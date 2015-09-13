+++
weight = 4
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "architecture"
categories = [ "overview" ]
+++

Monasca is a highly performant, scalable, fault-tolerant and extensible micro-services messages bus based architecture. <!--more-->
It uses a REST API for high-speed metrics processing and querying and has a streaming alarm engine and notification engine. 
All of the major components are linked using [Kafka](https://kafka.apache.org/).
Every component in the system is built with High Availability (HA) in mind and can be scaled either horizontally or vertically to allow for monitoring of very large systems.
![Monasca Metrics Architecture](/img/architecture/metrics-architecture.png)

#### metrics
The [Monasca API](/components/api/) is the gateway for all interaction with Monasca. In a typical scenario [metrics](/components/metrics)
are collected by the [Monasca Agent](/components/agent/) running on a system and sent to the Monasca API. The API then published the metrics to the Kafka queue.
From here the [Monasca Persister](/components/persister/) consumes metrics and writes them to our [Metrics database](/components/metrics_db/). The
[Monasca Threshold Engine](/components/alarms/) also consumes the metrics and uses them to evaluate [alarms](/components/alarms/).

At this point the metrics are in our system and can be be queried using the Monasca API, either directly or through one of our other components, such as the Horizon plugin or the [Monasca CLI](/components/cli).

When the Threshold Engine evaluates the metrics against the alarms it can create alarm state transition events.
These are published back to Kafka and are read by both the persister and [Notification Engine](/components/notifications/).
The Persister writes the alarm transitions to the DB for future retrieval.
The notification engine will send a notification of the configured type for appropriate state transitions.

In addition to the components discussed above we also have a configuration database used for storing information such as alarm definitions and notification methods.
This database can be either MySQL or PostgreSQL.

#### complex event processing (CEP)

Support for Complex Event Processing (CEP) is in process.
There are three additional components that will be added for events processing:

1. monasca-events-api
2. monasca-events-transform
3. monasca-events-engine

![Monasca Log Architecture](/img/architecture/events-architecture.png)

#### log processing

Support for Log processing is in progress and includes the following components:

1. Monasca Log API (monasca-log-api)
2. Monasca Log Parser (monasca-log-parser)
3. Monasca Log Persister (monasca-log-persister)

![Monasca Log Architecture](/img/architecture/log-architecture.png)

#### combined architecture

One of the goals of Monasca is to provide a single unified service for metrics, events and log processing.
The overall combined Monasca architecture can be shown as:

![Monasca Log Architecture](/img/architecture/combined-architecture.png)

#### future extensions

In addition, to the event and log processing systems a proof-of-concept had been developed for anomaly detection and metrics transform and aggregation engine.

![Monasca Log Architecture](/img/architecture/architecture.png)
