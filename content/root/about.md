+++
weight = 1
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "about"
categories = [ "Basics" ]
+++

Monasca provides an open-source multi-tenant, highly scalable, performant, fault-tolerant monitoring-as-a-service solution for metrics.
Metrics can be published to the Monasca API, stored and queried.
Alarms can be created and notifications, such as email, can be sent when alarms transition state.
Support for complex event processing and logging is in progress.
Monasca builds an extensible platform for advanced monitoring services that can be used by both operators and tenants to gain operational insight and visibilty, ensuring availabilty and stability.

##### Who is involved?

Monasca is in the process of applying for [OpenStack](http://www.openstack.org/) governance.
Currently, Monasca is hosted in in Github under the Stackforge organization, and will move to OpenStack.
All code has been developed under an Apache 2.0 license and has no restrictions on distribution or deployment.

Companies involved with developing and/or deploying Monasca include the following:

- Hewlett-Packard
- Time Warner Cable (TWC)
- Fujitsu
- Cisco
- Cray
- Rackspace

##### Technologies

Monasca is written in both Java and Python. Several of the componenent in Monasca started out in Java. However, the go-forward language for Monasca is Python.

Monasca is built on several open-source technologies including: <!--more-->

- [StackTach.v3](http://stacktach.com/) Real-time event stream processing system. StackTach.v3 is used in the Monasca Event processing system that is under development.
- [Apache Kafka](http://kafka.apache.org/) A high-throughput distributed messaging system. Kafka is a central component in Monasca and provides the infranstructure for all internal communications between components.
- [Apache Storm](https://storm.apache.org/) Apache Storm is a free and open source distributed realtime computation system. Apache Storm is used in the Monasca Threshold Engine.
- [Apache ZooKeeper](https://zookeeper.apache.org/) Apache ZooKeeper is is by Kafka and Storm.
- [InfluxDB](https://influxdb.com/) An open-source distributed time series database with no external dependencies. InfluxDB is one of the supported databases for storing metrics and alarm history. 
- [MySQL](https://www.mysql.com/) MySQL is a freely available open source Relational Database Management System (RDBMS) that uses Structured Query Language (SQL). SQL is the most popular language for adding, accessing and managing content in a database. It is most noted for its quick processing, proven reliability, ease and flexibility of use. MySQL is one of the supported databases for the Monasca Config Database.

In addition, Monasca optionally supports the following:

- [HP Vertica](http://www.vertica.com/) HP Vertica delivers the most advanced SQL analytics as a standards-based relational database with full support for SQL, JDBC, and ODBC. Vertica is one of the supported databases for storing metrics and alarm history.

##### Acknowledgments

Monasca uses [YourKit](https://www.yourkit.com/) Profiler for Java development and performance analysis.

[![Alt text](https://www.yourkit.com/images/yklogo.png "YourKit")](https://www.yourkit.com/)
