---
layout: post
title:  "Big Data Distributed Systems in 2014. Data processing."
date:   2013-12-30 21:52:07
categories: tech
---
By now [Hadoop](http://hadoop.apache.org/) has become the key element of almost every data-driven distributed system that can live with batch processing. Systems that cannot accept batching typically use [Storm](http://storm-project.net/) which has emerged as the leading framework for realtime processing of streaming data. The project to watch is [Spark](http://spark.incubator.apache.org/) which is on the path to become the unified data-processing framework and it is set to grow fast this year.

The adoption of Hadoop happened in part because lots of systems can tolerate batching of data processing tasks. What also helped Hadoop's raise is the fact that it is a general-purpose framework suitable for a large set of use-cases. With several competing distributions, a growing set of specialized tools, it really achieved the leader's status. 

The quest for higher performance drives the evolutions of these systems. When it comes to data processing the bottleneck is disk i/o. The moment the data needs to be written out to disk is the moment the performance of the overall system takes a hit. The phrase "Disk is the new tape" has been coined a few years ago to describe this reality. 

Hadoop and many data processing tools still assume the disk as the  storage medium, even for intermediate data. Next year we'll see the continued emergence of in-memory systems that use RAM as the primary storage while maintaining reliability. 

[Spark](http://spark.incubator.apache.org/) offers a general execution model that can optimize arbitrary operator graphs, and supports in-memory computing, which lets it query data faster than disk-based engines like Hadoop. This allows for a sequence MapReduce jobs to be run without using the disk. The other Spark's addition is the ability to share data between compute nodes that perform the operations, again, all without touching the disk.

With these two primitives, systems for interactive queries, graph analysis and stream processing are being implemented on top of Spark. In essence, an alternative of Hadoop's toolset is being developed on top of the same unified general-purpose engine.

The benefits of Spark go beyond dramatic performance increase due to in-memory processing. Another key benefit is the ability to combine different types of systems (ad-hoc queries, graph processing, machine learning, streaming) without having to export/import data from one to another.
 
My prediction for 2014 is that Spark will be the fastest growing general-purpose data processing technology. Several big distributed systems will use Hadoop/Spark hybrid architecture by replacing Hadoop MapReduce jobs to Spark engine, while still using data from HDFS. In 24 months Spark and it's eco-system will displace Hadoop MapReduce as typical way to run MapReduce.

Another big goal of Spark project is to improve usability and productivity of dig data technologies. [Let's look](/tech/2013/12/30/Big-Data-Distributed-Systems--Big-gains-in-usability-and-productivity-in-2014.html) at what could happen in 2014 in this area.