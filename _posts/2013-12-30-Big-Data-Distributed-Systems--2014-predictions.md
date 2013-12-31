---
layout: post
title:  "Big Data Distributed Systems. 2014 predictions."
date:   2013-12-30 21:52:07
categories: tech
---
Here's my take some technology advances in 2014. They are all related to Distributed Systems, but they serve different needs and solve different problems. The list below isn't meant to be comprehensive as I only focus on what I think will become the most impactful *new* projects that we'll hear more about in 2014.

# Infrastructure
- [Google Compute Engine](cloud.google.com/products/compute-engine/) will become the biggest [AWS](aws.amazon.com/) competitor, but won't make a dent in AWS growth and usage.
- Several large commercial data-driven distributed systems will be running on [Docker](www.docker.io).
- Docker will enable at least one use-case previously impossible due to the wight of the virtualization layer.
- At least two large-scale distributed systems will forgo virtualization in favour of running on Docker with [CoreOS](coreos.com).
- [Redis Sentinel](redis.io/topics/sentinel) will be used as a fully-featured alternative to [ZooKeeper](zookeeper.apache.org) in a large-scale distributed system. 

My reasoning is [here](/tech/2013/12/30/Infrastructure-for-distributed-systems--2014-technologies-to-watch.html).

# Data processing
- [Spark](spark.incubator.apache.org) will be the fastest growing general-purpose data processing technology. Several big distributed systems will use Hadoop/Spark hybrid architecture by replacing Hadoop MapReduce jobs to Spark engine, while still using data from HDFS.
- In 24 months Spark and it's eco-system will displace Hadoop MapReduce as typical way to run MapReduce.

My reasoning is [here](/tech/2013/12/30/Big-Data-Technologies-growing-in-2014.html).

I can't wait for the beggining of 2015 to check back on these predictions!




