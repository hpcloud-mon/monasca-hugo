+++
weight = 4
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "architecture"
categories = [ "overview" ]
+++

Monasca is a highly performant, scalable, fault-tolerant and extensible micro-services messages bus based architecture. <!--more-->
It uses a REST API for high-speed metrics processing and querying and has a streaming alarm engine and notification engine. All of these are linked
using the [Kafka](https://kafka.apache.org/).
Every component in the system is built with High Availability (HA) in mind and can be scaled either horizontally or vertically to allow for monitoring of very large systems.
![Monasca Metrics Architecture](/img/architecture/metrics-architecture.png)

#### Metrics/Alarm Flow
The [Monasca API](/components/api/) is the gateway for all interaction with Monasca. In a typical scenario [metrics](/components/metrics)
are collected by the [Monasca Agent](/components/agent/) running on a system and sent to the Monasca API. The API then published the metrics to the Kafka queue.
From here the [Monasca Persister](/components/persister/) consumes metrics and writes them to our [Metrics database](/components/metrics_db/). The
[Monasca Threshold Engine](/components/alarms/) also consumes the metrics and uses them to evaluate [alarms](/components/alarms/).

At this point the metrics are in our system and can be be queried using the Monasca API, either directly or through one of our other components, such as the Horizon plugin or the [Monasca CLI](/components/cli).

When the Threshold Engine evaluates the metrics against the alarms it can create alarm state transition events. These are published back to Kafka
and are read by both the persister and [Notification Engine](/components/notifications/). The persister simply writes the alarm transitions to the
DB for future retrieval. The notification engine will send a notification of the configured type for appropriate state transitions.

In addition to the components discussed above we also have a configuration database used for storing information such as alarm definitions and
notification methods. This db can be either mysql or postgresql.

**Future Components**

Support for Complex Event Processing (CEP) and Logging is in process. There are three additional components that will be added for events processing:

1. monasca-events-api
2. monasca-events-transform
3. monasca-events-engine

Similarly, for log processing, there are several components being added:

1. monasca-log-api
2. monasca-log-transform
3. monasca-log-persister

![Monasca Log Architecture](/img/architecture/log-architecture.png)

![Monasca Log Architecture](/img/architecture/metrics-log-architecture.png)

In addition, a proof-of-concept has been started for an anomaly detection engine.
