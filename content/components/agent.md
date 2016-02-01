+++
weight = 7
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "agent"
categories = [ "Components" ]
+++

Monasca supports an optional monitoring [agent](https://github.com/openstack/monasca-agent) that is written in Python. <!--more-->
The Agent is a Python program that runs on systems and runs various checks then sends the data on to the [Monasca API](/components/api/).
Checks the Agent can run include:

- System metrics: cpu, memory, network, disk and file-system utilization.
- Service metrics: The agent supports plugins such as MySQL, RabbitMQ, Kafka, and many others.
- Statsd: Statsd metrics can be sent locally to the agent which will format and send on to the Monasca API.
- Nagios: The Agent can run any Nagios check and convert the results to a metric and send to the Monasca API. Status code and messages are sent as 'value_meta" in the metric.
- Check_mk: Similar to Nagios checks the Agent can run check_mk checks.

More details on the Agent can be found at these pages:

- [Architecture and Installation](https://github.com/openstack/monasca-agent/blob/master/docs/Agent.md)
- [Agent Plugins](https://github.com/openstack/monasca-agent/blob/master/docs/Plugins.md)
- [Customizing the Agent](https://github.com/openstack/monasca-agent/blob/master/docs/Customizations.md)
- [Metrics and the Agent](https://github.com/openstack/monasca-agent/blob/master/docs/MonascaMetrics.md)
