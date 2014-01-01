---
layout: post
title:  "Big Data Distributed Systems. 2014 predictions."
date:   2013-12-30 21:52:07
categories: tech
---
To follow end of year tradition and to keep myself accountable I figured I should write down some predictions about Infrastructure-as-a-Service and Data Processing technologies.

## Infrastructure
- [Google Compute Engine](https://cloud.google.com/products/compute-engine/) will become the biggest [AWS](https://aws.amazon.com/) competitor, but won't make a dent in AWS growth and usage.
- Several large commercial data-driven distributed systems will be running on [Docker](https://www.docker.io).
- Docker will enable at least one use-case previously impossible due to the weight of the virtualization layer.
- At least two large-scale distributed systems will forgo virtualization layer in favour of running on Docker with [CoreOS](https://coreos.com), without VMs.
- [Redis Sentinel](http://redis.io/topics/sentinel) will be used as a fully-featured alternative to [ZooKeeper](http://zookeeper.apache.org) in a large-scale distributed system. 

What are the reasons behind these predictions? Here's my [reasoning](/tech/2013/12/30/Infrastructure-for-distributed-systems--2014-technologies-to-watch.html).

## Data processing
- [Spark](http://spark.incubator.apache.org) will be the fastest growing general-purpose data processing technology. Several big distributed systems will use Hadoop/Spark hybrid architecture by replacing Hadoop MapReduce jobs to Spark engine, while still using data from HDFS.
- In 24 months Spark and it's eco-system will displace Hadoop MapReduce as typical way to run MapReduce.

My reasoning is [here](/tech/2013/12/30/Big-Data-Technologies-growing-in-2014.html).

I can't wait for the beginning of 2015 to check back on these predictions!




