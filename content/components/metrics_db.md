+++
Categories = ["components"]
date = "2015-08-19T15:23:18-06:00"
title = "metrics_db"
weight = 10

+++

Metrics and alarm state transitions are persisted to a Metrics DB from which they can be retrieved at any time.<!--more-->
As Monasca is built for scale a specific database that can handle the high metrics load is needed for this use case.

Monasca supports two different metrics databases, [Vertica](http://www.vertica.com/) and [InfluxDB](https://influxdb.com/). The two components
that interact with the Metrics DB are the [persister](/components/persister/) and the [API](/components/api/). These can both be configured to
use either database.

For both databases the schema used is found in the [Ansible](http://www.ansible.com/home) role, [monasca-schema](https://github.com/hpcloud-mon/ansible-monasca-schema).
