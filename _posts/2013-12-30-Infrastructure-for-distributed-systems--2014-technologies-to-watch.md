---
layout: post
title: Big Data Distibuted Systems in 2014. Infrastructure.
categories: tech
published: true
---

In 2013 and prior, the concept of public IaaS has been well established by [AWS EC2](http://aws.amazon.com/ec2) and adjacent AWS technologies - a utility-based service that provides access to elastic compute resources. What followed are several adaptations of these core concepts to the private cloud. In 2014 we should see some changes to the status quo.

## Google Compute Engine
In 2014 we'll see the first real competitor of EC2: [Google Compute Engine](https://cloud.google.com/products/compute-engine/). I won't bore you with the talk about Google's deep pockets to fight the price war with Amazon. But it is important to note that Google does have at least one technology advantage. Google would be using dedicated finer that connects its data centres, while Amazon uses the public internet. As a result, globally-distributed systems stand to gain in network performance and predicability.

In 2014 GCE will not make a dent in AWS growth and usage, but will likely provoke some reaction from AWS which will likely take the form of further price reductions.  

## Docker
EC2, GCE, CloudStack, OpenStack are all using the same basic virtualization approach: the user of the service requests a compute instance and gets a complete VM. Because the instance is a VM it is fully isolated from other instances and the user gets to define and manage the entire configuration of the instance, down to the choice of the OS kernel. This principle remained unchallenged pretty much since the advent of virtualization with Xen and vSphere. 

As a result of this principle, the process of creation of a new instance was akin to booting a new server. Each physical server would run a single copy of the OS, plus the hypervisor (Xen or VMWare or similar), plus the user's choice of OS for every instance. The remainder of the machines resources would be allocated to the actual application.

[Docker](https://www.docker.io) uses a different approach and changes the interface. Rather than creating a VM, it creates a "container" - a runtime environment that uses much less resources than a VM. The "catch" is, all docker containers share the same OS kernel. In turns out that for a distributed system this constraint isn't particularly honours. Because such systems generally use the same OS kernel for their compute nodes even when running on traditional IaaS that offer this level of flexibility. So Docker containers provide application isolation, security and deployment consistency without the overhead of an entire VM. 

Docker containers boot extremely fast - in milliseconds. Compared to tens of seconds it takes to boot a VM, this speed-up is so fundamental, it will create a whole new use-cases for infrastructure.


## CoreOS
When everything is running inside Docker containers, the next logical step becomes making sure that the the host OS is configured for this specific purpose.

Server-side linux distributions come in variety of shapers and generally strive to support many use-cases. On the other hand, [CoreOS](http://coreos.com) Linux distribution has the singular focus. To create the most optimal Linux distribution to run Docker. This single-purpose focus leads to the most optimal utilization of resources - an important aspect of large-scale distributed systems. The CoreOS project has ambitions beyond creating a great single-purpose Linux distro. The team is on the mission to "provide the tools to create and run distributed platforms".


## Service discovery, coordination, configuration
Past certain scale a distributed system needs an internal service for state tracking, configuration and service discovery within a distributed system.

Here's how one such system, [ZooKeeper](http://zookeeper.apache.org/), describes it's role:

*ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. All of these kinds of services are used in some form or another by distributed applications. Each time they are implemented there is a lot of work that goes into fixing the bugs and race conditions that are inevitable. Because of the difficulty of implementing these kinds of services, applications initially usually skimp on them ,which make them brittle in the presence of change and difficult to manage. Even when done correctly, different implementations of these services lead to management complexity when the applications are deployed.*

As the use-cases of such a system are being more widely [understood](https://news.ycombinator.com/item?id=6366665) there will be other, simpler, standalone, lightweight implementations of coordination and service discovery services. 

Some high potentials include [Redis](http://redis.io) managed by with it's upcoming [Sentinel](http://redis.io/topics/sentinel) module, [Serf](http://www.serfdom.io/), [SkyDNS](http://blog.gopheracademy.com/skydns) or [etcd](http://coreos.com/using-coreos/etcd/) being developed as part of CoreOS.

Next, let's look at [data processing technologies in 2014](/tech/2013/12/30/Big-Data-Technologies-growing-in-2014.html) that are poised to grow.