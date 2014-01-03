---
layout: post
title:  "Big Data Distributed Systems in 2014. Usability and productivity"
date:   2013-12-30 21:52:07
categories: tech
---
The tools and platforms for data-driven distributed systems are still far too difficult to use even for very experienced software engineers. Because of this, the progress of adoption is much slower than the real-world need would dictate. There are huge numbers of projects that don't get to use the right tools for their needs simply because their owners find it too difficult to understand.

In 2014 this area will see advances in a few broad areas

## Ease of development: Go language
[Derek Collison](https://twitter.com/derekcollison‎) made a [prediction](https://twitter.com/derekcollison/status/245522124666716160) that [Go](http://golang.org) will become the dominant language for systems work in IaaS, Orchestration, and PaaS in 24 months. That was 15 months ago and things are really on track for it to be pretty accurate. The language's use in distributed systems is growing fast. It's amazing how much traction this new language has received (even without generics).

After having spent years coding systems in C++, Python and Java, with my limited experience with Go I can see how the language makes the coding process faster without sacrificing efficiency of the resulting code.

## Ease of development: dev environment
Working on a sub-system of a large distributed system means spending enormous amount of time on setup and configuration of the development environment that approximates the real-life system along with real-life datasets.

[Vagrant](http://www.vagrantup.com/) is the technology to build and distribute development environments for distributed systems. It offers a front-end to desktop hypervisors and AWS. Rather than offering a point-and-client UI Vagrant users describe the environment in a single file named Vagrantfile that can be committed along with the code. Once Vagrantfile is created developers create consistent reproducible environments on their desktops or on AWS. No additional dependencies are required. When an environment is created on a desktop for the first time, vagrant pulls the VM images and caches them on the local machine. 

## Ease of deployment: PaaS
2013 was the year of true explosion of different PaaS frameworks. It reminded me the time around 2005. At that time [Ruby on Rails](http://rubyonrails.org/) has established the core primitives of a modern Web framework and it seemed that the innovation around Web frameworks may be complete. The opposed happened - there was an explosion of smaller more specific frameworks.

Same is happening today with PaaS. [Heroku](http://heroku.com) and [CloudFoundry](http://www.cloudfoundry.com/) together have established the basic expectations from a PaaS layer - language-agnostic, infrastructure-agnostic environment where app developers simply expect the availability of a rich set of services for their apps. All that, wrapped in a simple interface letting developers deploy to production.

Heroku remains a leading PaaS. The world owes Heroku two fundamental primitives for PaaS. First is the developer's experience of [deploying apps with git](https://devcenter.heroku.com/articles/git). The second is the concept of [buildpacks](https://devcenter.heroku.com/articles/buildpacks) as a way to extend PaaS ability to host apps for a specific language or runtime. Given it's closed-source nature and rigid ties with underlying infrastructure, it is difficult to see how it would become the foundation for all the world's distributed systems. But these primitives are being widely adopted by various PaaS implementations.

2013 saw the birth of many PaaS frameworks: [Flynn](https://flynn.io/), [Deis](http://deis.io/), [Stratos](http://stratos.incubator.apache.org/). CloudFoundry is growing fast, with [several](https://www.appfog.com/) [hosted](http://static.com/) deployments and growing eco-system. At the opposite scale of complexity is [Dokku](http://progrium.com/blog/2013/06/19/dokku-the-smallest-paas-implementation-youve-ever-seen/) - the smallest PaaS created by combining separate standalone primitives such as Docker, buildpacks and git-based app deployment into a real PaaS.

2014 will see further componentization of PaaS and growth of usage particularly favouring smaller, simpler to deploy and easier-to-understand PaaS alternatives.

## Common methodology
Finally, the list of 2014 technologies to watch would not be complete without mentioning [12 factor methodology](http://12factor.net/), an important document that received lots of attention in 2013. The principles defined in this document is a true a crystallization of collective experience of many people who have build hundreds of apps and learned their lessons.

This manifest-like document is a modern analog of [Design Patterns](http://en.wikipedia.org/wiki/Design_Patterns) or [Refactoring](http://en.wikipedia.org/wiki/Refactoring). 

I expect that this document will provide the common vocabulary and a common set of principles and priorities for software engineers that develop and operate apps that make up distributed systems. In 2014 I hope to see a set of factors that define the methodology for modern distributed systems. 