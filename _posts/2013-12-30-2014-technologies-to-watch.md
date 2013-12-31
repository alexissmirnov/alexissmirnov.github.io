---
layout: post
title:  "Most important technologies in 2014. Big Data Distributed Systems"
date:   2013-12-30 21:52:07
categories: tech
---

# tl/dr: Hot in 2014 
- Docker
- CoreOS
- GAE
- Redis Sentinel as service discovery and co-ordination
- Spark
- Go
- Docker-based PaaS
- 12factor

# Most important technologies in 2014. Big Data Distributed Systems
End of the year is the time for reflection, for looking back at the past year and looking forward into the next year trying to predict what the future holds. So what technology will be most important in the future?

Ask this question without imposing any constrains and you may get answers about energy, space exploration, biology, artificial intelligence. The most important technologies of the future will be those that solve the biggest problems or provide the most powerful tools.

What's fascinating about all these technologies, is that they have something in common: software. Two and a half years ago Marc Andressen penned an highly influential essay titled "Why Software is Eating the World". His central thesis remains true today: more and more industries "from movies to agriculture to national defence" are becoming largely software industries. Software is becoming the key part of solving the biggest problems. The most powerful tools of the future will be software tools.

If software will be at the center of most important technologies of the future, let's restate the question. Which software technologies will be the most important? To me this question is of profound importance. Time and energy invested in these software technologies would have a compounded effect, accelerating solutions to world's biggest problems and creating the most powerful tools.

I argue that distributed systems or, more specifically, big data distributed systems will be the most important software technology of the future.

The world's data is growing at compounded annual growth rate of around 45%, which means a 44X increase in the next 10 years. This is a direct consequence of entire industries becoming software-based, a direct outcome of "software eating the world". Distributed system that stands a chance to solve a big problem needs to deal with datasets that follow such growth rate.

Big Data Distributed Systems are those systems that generate, collect, process, analyze and ultimately derive value from large and fast-growing datasets. They run on a very large number of compute nodes and serve millions of consumers.

Aren't there tremendous advances in other types of software technologies? Why would, say, mobile apps or HTML5 or augmented reality have the bigger impact on the future? The reasons are twofold.

First, technologies that deliver breakthrough user experiences of the future (via mobile apps, web apps, wearable apps) all will rely to large extent on data-driven distributed systems providing much of the value. For example, when a Maps app on your iPhone informs you of the heavy traffic up ahead, it surfaces the results of the work performed by a data-driven distributed system.

Second, any system that solves a big problem in any industry will run on a distributed system, and much of those systems will use large and growing datasets. A true artificial intelligence that rivals the ability of the human brain will run one. The breakthrough in clean energy will also run on one.

The fact that foundational technologies have disproportionate impact on our lives should be surprising. We've seen this before. Advances in transportation enabled trade. Advances in electrical grid spurred so many transformational technologies that rely on electricity. Data-driven distributed systems is one of those foundational technologies.

These systems are so essential, yet they are also very new. Their adoption outside of leading internet giants has really just started over the last few years. Their fundamentals are still in active development. There is no way to know for sure what specific technologies will be at the hart of such systems in 10 years. But things are more clear looking one year ahead.

Below is my take on which technologies will emerge in 2014. They are all related to distributed systems, but they serve different needs and solve different problems. The list below isn't meant to be comprehensive as I only focus on what I think will become the most impactful new projects that we'll hear more about in 2014.

# Infrastructure layer
By 2013 and prior, the concept of public IaaS has been well established by AWS EC2 and adjacent AWS technologies - a utility-based service that provides access to elastic compute resources. What followed are several adaptations of these core concepts to the private cloud. But there have not been a viable alternative to EC2.

## Google Compute Engine
In 2014 we'll see the first real competitor of EC2: Google Compute Engine. I won't bore you with the talk about Google's deep pockets to fight the price war with Amazon. But it is important to note that Google does have at least one technology advantage. Google would be using dedicated finer that connects its data centres, while Amazon uses the public internet. As a result, globally-distributed systems stand to gain in network performance and predicability.

In 2014 GAE will not make a dent in AWS growth and usage, but will likely provoke some reaction from AWS which will likely take the form of further price reductions.  

## Docker
EC2, GCE, CloudStack, OpenStack are all using the same basic virtualization interface: the user of the service gets a complete compute instance. The instance is fully isolated from other instances and the user gets to define and manage the entire configuration of the instance. This principle remained unchallenged pretty much since the advent of virtualization with Xen and vSphere. 

As a result of this principle, the process of creation of a new instance was akin to booting a new server. Each physical server would run a single copy of the OS, plus the hypervisor (Xen or VMWare or similar), plus the user's choice of OS for every instance. The remainder of the machines resources would be allocated to the actual application.

Docker uses a different approach and changes the interface. Rather than creating a VM, it creates a "container" - a runtime environment that uses much less resources than a VM. The "catch" is, all docker containers must share the same OS kernel. In turns out that for a distributed system this constraint isn't particularly honours. Because such systems generally use the same OS kernel for their compute nodes even when running on traditional IaaS that offer this level of flexibility. So Docker containers provide application isolation, security and deployment consistency without the overhead of an entire VM. 

Docker containers boot extremely fast - in milliseconds. Compared to tens of seconds it takes to boot a VM, this speed-up is so fundamental, it will create a whole new use-cases for infrastructure.

My predictions for 2014:
- At least one commercial data-driven distributed system running on Docker.
- At least one new use-case for elastic compute infrastructure, previously impossible due to the wight of the VM.

## CoreOS
When everything is running inside Docker containers, the next logical step becomes making sure that the the host OS is configured for this specific purpose.

Server-side linux distributions come in variety of shapers and generally strive to support many use-cases. On the other hand, CoreOS singular focus is to create the most optimal Linux distribution to run Docker. This single-purpose focus leads to the most optimal utilization of resources - an important aspect of large-scale distributed systems.

My prediction for 2014 is that at least two distributed systems will be running on CoreOS/Docker infrastructure using dedicated hardware, without VM overhead.

## Service discovery, coordination, configuration
Past certain scale it is easier to introduce a runtime service for state tracking, configuration and service discovery within a distributed system.

Here's how one such system, ZooKeeper, describes it's role.

ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. All of these kinds of services are used in some form or another by distributed applications. Each time they are implemented there is a lot of work that goes into fixing the bugs and race conditions that are inevitable. Because of the difficulty of implementing these kinds of services, applications initially usually skimp on them ,which make them brittle in the presence of change and difficult to manage. Even when done correctly, different implementations of these services lead to management complexity when the applications are deployed.

As the use-cases of such a system are being more widely understood (https://news.ycombinator.com/item?id=6366665) there will be other, simpler, more lightweight implementations of coordination and service discovery systems. 

My prediction for 2014, we'll learn about at least one fully-featured alternative to ZooKeeper used in a large-scale distributed system. Possible contenders could be redis managed by with it's upcoming sentinel module, Serf, SkyDNS or etcd.

# Data processing
By now Hadoop has become the key element of almost every data-driven distributed system. It happened because lots of systems can tolerate batching of data processing tasks. What also helped Hadoop's raise is the fact that it is a general-purpose framework suitable for a very large set of use-cases. With several competing distributions, a growing set of specialized tools, it really achieved the leader's status. Systems that cannot accept batching use Storm which has emerged as the leading framework to process streaming data.

Performance impacts the overall performance of these systems. The bottleneck is i/o performance, specifically disk i/o. The moment the data needs to be written out to disk is the moment the performance of the overall system takes a big hit. The phrase "Disk is the new tape" has been coined a few years ago to describe this reality. 

Many data processing tools still assume the disk as the primary storage medium. The typical way to run Hadoop is to store the data on disks in HDFS or a distributed key/value store such as HBase. Next year we'll see the continued emergence of systems that use memory as the primary storage. Exporting data from memory would be increasingly considered a slow and infrequent operation.

The technology to watch in this space is Spark, an in-memory data processing engine that provides alternative to general-purpose Hadoop. Spark introduces a way to organize data processing operators into a sequence (more precisely a DAG). This feature allow to sequence MapReduce jobs and run them without using the disk. The other Spark's addition is the ability to share data between compute nodes that perform the operations, again, without touching the disk.

With these two primitives, systems for interactive queries, graph analysis and stream processing are being implemented. In essence, an alternative of Hadoop's toolset is being developed on top of the same unified general-purpose engine.

The benefits of Spark go beyond dramatic performance increase due to in-memory processing. The key benefit is the ability to combine different types of systems (ad-hoc queries, graph processing, machine learning, streaming) without having to export/import data from one to another.
 
My prediction for 2014 is that several big distributed systems will replace Hadoop MapReduce jobs to Spark engine, while still using data from HDFS.


# Ease of use and developer productivity
The tools and platforms for data-driven distributed systems are still far too difficult to use even for very experienced software engineers. Because of this, the progress of adoption is much slower than the real-world need would dictate. There are huge numbers of projects that don't get to use the right tools for their needs simply because their owners find it too difficult to understand.

This area will see advances in these broad areas

## Ease of development: language
Derek Collison made prediction that Go will become the dominant language for systems work in IaaS, Orchestration, and PaaS in 24 months. That was 15 months ago and it really is on track to be pretty accurate. In fact many technologies mentioned above are written in Go and the language's use just keeps growing. It's amazing how much traction this new language has received (even without generics).

I have spent years coding systems in C++, Python and Java. In my limited experience with Go it is easy to see how the language makes the coding process faster without sacrificing efficiency of the resulting code.

## Ease of development: dev environment
Working on a sub-system of a large distributed system means spending enormous amount of time on setup and configuration of the development environment that approximates the real-life system along with real-life datasets.

Vagrant is the technology to build and distribute development environments for distributed systems. It offers a front-end to desktop hypervisors and AWS. Rather than offering a point-and-client UI Vagrant users describe the environment in a single file named Vagrantfile that can be committed along with the code. Once Vagrantfile is created developers create consistent reproducible environments on their desktops or on AWS. No additional dependencies are required. When an environment is created on a desktop for the first time, vagrant pulls the VM images and caches them on the local machine. 

## Ease of deployment: PaaS
2013 was the year of true explosion of different PaaS frameworks. It reminded me the time around 2005. At that time Ruby on Rails has established the core primitives of a modern Web framework and it seemed that the innovation around Web frameworks has been complete. The opposed happened - there was a true explosion of smaller more specific frameworks.

Same is happening today with PaaS. Heroku and CloudFoundry has established the basic characteristics of what should be expected from a PaaS layer - language-agnostic, infrastructure-agnostic environment where app developers simply expect the availability of a rich set of services they need. All that, wrapped in a simple interface letting developers deploy to production.

Heroku remains an excellent PaaS. The world owes Heroku two fundamental primitives for modern PaaS. First is the developer's experience of deploying apps via git. The second is the concept of buildpacks as a way to extend PaaS ability to host apps for a specific language or runtime. But given it's closed-source nature and rigid ties with underlying infrastructure, it is difficult to see how it would become the foundation for all the world's distributed systems.

2013 saw the birth of many PaaS frameworks: Flynn, Deis, Stratos, several hosted deployments of CloudFoundry. An exciting addition to this list is Dokku - world's smallest PaaS by combining separate standalone primitives such as Docker, buildpacks and git-based app deployment into a real PaaS.

2014 will see further componentization of PaaS and growth of usage particularly favouring smaller, simpler and easier-to-understand PaaS alternatives.

## Common methodology
Finally, the list of 2014 technologies to watch would not be complete without mentioning 12 factor methodology, an important document that received lots of attention in 2013. The principles defined in this document is a true a crystallization of collective experience of many people who have build hundreds of distributed systems and learned their lessons.

Not a technology per-se, this manifest-like document is a modern analog of Software Design Patterns or Refactoring. 

I expect that this document will provide the common vocabulary and a common set of principles and priorities for engineers involved in development and operation of distributed systems.





Data-driven distributed systems are the technology of the future.

Start with a question: what technology will be the most important one in the future.


Now let's qualify. What kind of software this is? These are distributed systems. Many servers, many more clients.

Let's further qualify: systems that distribute computation, network, data. Interrelated, but the biggest driver for evolution of these systems will be data. Data collection, data processing.

There are many recent technologies that excite me. The year was full with advances in Distributed Systems. Big Data has become just as vague of a term as Distributed Systems.

# Developer productivity

Vagrant has really simplified the setup and management of virtual machines that accurately approximate the production environment.

2014 will see further shrinking the gap between a developer and production environment.

Modularization of PaaS: etcd (flynn), dokku
buildpacks
Architecture: 12 factor manifest.

# IaaS
For years now compute resources were allocated and managed in essentially the same way, though virtualization. 2013 was the year of a break-though with Docker.

## CoreOS

# Decoupling of PaaS
It started with buildpacks from Heroku, discovery service based on smaller primitives such as reliable k/v store that can be a basis of service discovery, configuration and coordination capabilities. Like etcd (or ZooKeeper)

