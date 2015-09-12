+++
weight = 4
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "architecture"
categories = [ "overview" ]
+++

Monasca is a highly performant, scalable, fault-tolerant and extensible micro-services messages bus based architecture. <!--more-->

It uses a REST API for high-speed metrics processing and querying and has a streaming alarm engine and notification engine. All of these are linked
using the messaging system [Kafka](https://kafka.apache.org/). Every component in the system is built with High Availability in mind and can grow
horizontally to allow for monitoring of very large systems.
![Monasca Architecture](/img/Monasca-arch-component-diagram.png)

#### Metrics/Alarm Flow
The [Monasca API](/components/api/) is the gateway for all interaction with Monasca. In a typical scenario [metrics](/components/metrics)
are collected by the [Monasca Agent](/components/agent/) running on a system and sent to the Monasca API. The api then puts the metrics onto the Kafak queue.
From here the [Monasca Persister](/components/persister/) consumes metrics and writes them to our [Metrics database](/components/metrics_db/). The
[Monasca Threshold Engine](/components/alarms/) also consumes the metrics and uses them to evaluate [alarms](/components/alarms/).

At this point the metrics are in our system and can be be retrieved from the Monasca API, either directly or through one of our other components
such as the Horizon plugin or the [Monasca CLI](/components/cli).

When the threshold engine evaluates the metrics against the alarms it can create alarm state transition events. These are published back onto Kafka
and are read by both the persister and [Notification Engine](/components/notifications/). The persister simply writes the alarm transitions to the
DB for future retrieval. The notification engine will send a notification of the configured type for appropriate state transitions.

In addition to the components discussed above we also have a configuration database used for storing information such as alarm definitions and
notification methods. This db can be either mysql or postgresql.

**Future Components**

The events and transform engines are actively being worked on and will soon be incorporated. In addition some proof of concept work has been done
for an Anomaly detection engine.

