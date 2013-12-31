---
layout: post
title:  "Big Data Distributed Systems in 2014. Big gains in usability and productivity"
date:   2013-12-30 21:52:07
categories: tech
---
The tools and platforms for data-driven distributed systems are still far too difficult to use even for very experienced software engineers. Because of this, the progress of adoption is much slower than the real-world need would dictate. There are huge numbers of projects that don't get to use the right tools for their needs simply because their owners find it too difficult to understand.

In 2014 this area will see advances in these broad areas

## Ease of development: Go language
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