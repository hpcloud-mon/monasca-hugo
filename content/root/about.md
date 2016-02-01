+++
weight = 1
date = "2015-08-19T18:32:00-06:00"
draft = false
title = "about"
categories = [ "overview" ]
+++

Monasca is an OpenStack project that provides an open-source multi-tenant, highly scalable, performant, fault-tolerant monitoring-as-a-service solution. <!--more-->
Metrics can be published to the Monasca API, stored and queried.
Alarms can be created and notifications, such as email, can be sent when alarms transition state.
Support for complex event processing and logging is in progress.
Monasca builds an extensible platform for advanced monitoring services that can be used by both operators and tenants to gain operational insight and visibilty, ensuring availabilty and stability.

##### presentations

Several overviews of Monasca can be found at the following:

- [Introducing Using Monasca for Production OpenStack Monitoring](https://www.openstack.org/summit/tokyo-2015/videos/presentation/congrats-you-stood-up-an-openstack-environment-but-now-they-want-you-to-monitor-it-introducing-using-monasca-for-production-openstack-monitoring)
- [Monasca Deep Dive](https://www.openstack.org/summit/openstack-paris-summit-2014/session-videos/presentation/monasca-deep-dive-monitoring-at-scale)
- [ELK and Monasca Crossing: Logging as an OpenStack Service](https://www.openstack.org/summit/tokyo-2015/videos/presentation/elk-and-monasca-crossing-logging-as-an-openstack-service)

Additional information on Monasca, including presentations at prior OpenStack conferences, can be found at the [Monasca Wiki](https://wiki.openstack.org/wiki/Monasca).

##### who is involved?

The members of the Monasca team are primarily composed of companies, organizations and individuals involved in development and deployment of OpenStack.

Some of the major companies involved with developing and/or deploying Monasca include the following:

- Hewlett Packard Enterprise
- Time Warner Cable (TWC)
- Fujitsu
- Cisco
- Cray
- Rackspace
- SAP
- NEC

##### technologies

Monasca is written in both Java and Python. Several of the components in Monasca started out in Java. However, the go-forward language for Monasca is Python.

Monasca is built on several open-source technologies including: <!--more-->

- [OpenStack](http://openstack.org): Monasca uses the [Keystone](http://docs.openstack.org/developer/keystone/) OpenStack Identity Service for authentication, authorization and multi-tenancy. Monasca integrates with several other OpenStack services such as [Heat](http://docs.openstack.org/developer/heat/) for auto-scaling and [Ceilometer](http://docs.openstack.org/developer/ceilometer/) for monitoring OpenStack resources. Integrations with additional OpenStack services will be targeted in the future.
- [Apache Kafka](http://kafka.apache.org/): A high-throughput distributed messaging system. Kafka is a central component in Monasca and provides the infranstructure for all internal communications between components.
- [Apache Storm](https://storm.apache.org/): A free and open source distributed realtime computation system. Apache Storm is used in the Monasca Threshold Engine.
- [Apache ZooKeeper](https://zookeeper.apache.org/): Used by Kafka and Storm.
- [InfluxDB](https://influxdb.com/): An open-source distributed time series database with no external dependencies. InfluxDB is one of the supported databases for storing metrics and alarm history. 
- [MySQL](https://www.mysql.com/): A freely available open source Relational Database Management System (RDBMS) that uses Structured Query Language (SQL). SQL is the most popular language for adding, accessing and managing content in a database. It is most noted for its quick processing, proven reliability, ease and flexibility of use. MySQL is one of the supported databases for the Monasca Config Database.
- [Grafana](http://grafana.org): An open source, feature rich metrics dashboard and graph editor. Support for Monasca as a data source in Grafana has been added.

In addition, Monasca optionally supports the following:

- [HP Vertica](http://www.vertica.com/): HP Vertica delivers the most advanced SQL analytics as a standards-based relational database with full support for SQL, JDBC, and ODBC. Vertica is one of the supported databases for storing metrics and alarm history within Monasca.

##### licensing

Monasca has been developed under an [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0) and has no restrictions on distribution or deployment.

##### acknowledgments

Monasca uses the [YourKit Java Profiler](https://www.yourkit.com/) for Java development and performance analysis.

[![Alt text](https://www.yourkit.com/images/yklogo.png "YourKit")](https://www.yourkit.com/)
