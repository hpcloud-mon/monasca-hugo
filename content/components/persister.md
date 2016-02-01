+++
Categories = ["components"]
date = "2015-08-19T15:23:05-06:00"
title = "persister"
weight = 10

+++

The [Monasca persister](https://github.com/openstack/monasca-persister) is responsible for reading metrics and alarm state transitions from
[Kafka](https://kafka.apache.org/) and writing to the [metrics DB](/components/metrics_db/).<!--more--> Though this is a relatively simple task it must
be done reliably at high speed with HA.

Multiple persisters can run simultaneously utilizing different partitions within a Kafka topic to share the
load between all instances. As instances drop off or come up the load is rebalanced between all available persisters.
