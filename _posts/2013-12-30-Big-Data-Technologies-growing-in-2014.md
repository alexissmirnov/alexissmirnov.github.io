---
layout: post
title:  "Big Data Technologies growing in 2014"
date:   2013-12-30 21:52:07
categories: tech
---
By now Hadoop has become the key element of almost every data-driven distributed system. It happened because lots of systems can tolerate batching of data processing tasks. What also helped Hadoop's raise is the fact that it is a general-purpose framework suitable for a very large set of use-cases. With several competing distributions, a growing set of specialized tools, it really achieved the leader's status. Systems that cannot accept batching use Storm which has emerged as the leading framework to process streaming data.

Performance impacts the overall performance of these systems. The bottleneck is i/o performance, specifically disk i/o. The moment the data needs to be written out to disk is the moment the performance of the overall system takes a big hit. The phrase "Disk is the new tape" has been coined a few years ago to describe this reality. 

Many data processing tools still assume the disk as the primary storage medium. The typical way to run Hadoop is to store the data on disks in HDFS or a distributed key/value store such as HBase. Next year we'll see the continued emergence of systems that use memory as the primary storage. Exporting data from memory would be increasingly considered a slow and infrequent operation.

The technology to watch in this space is Spark, an in-memory data processing engine that provides alternative to general-purpose Hadoop. Spark introduces a way to organize data processing operators into a sequence (more precisely a DAG). This feature allow to sequence MapReduce jobs and run them without using the disk. The other Spark's addition is the ability to share data between compute nodes that perform the operations, again, without touching the disk.

With these two primitives, systems for interactive queries, graph analysis and stream processing are being implemented. In essence, an alternative of Hadoop's toolset is being developed on top of the same unified general-purpose engine.

The benefits of Spark go beyond dramatic performance increase due to in-memory processing. The key benefit is the ability to combine different types of systems (ad-hoc queries, graph processing, machine learning, streaming) without having to export/import data from one to another.
 
My prediction for 2014 is that several big distributed systems will replace Hadoop MapReduce jobs to Spark engine, while still using data from HDFS.