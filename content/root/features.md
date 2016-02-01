+++
Categories = []
date = "2015-08-21T09:04:14-06:00"
title = "features"
weight = 2

+++

Monasca is designed to monitor a modern cloud infrastructure which is dynamic and large, these features have been designed with that in mind:<!--more-->

- The [Monasca API](/components/api/) is a REST API used for all interaction with the server stack providing easy extensibility.
- All components in the system are designed for High Availability and Scale. Each component can be horizontally scaled as needed and our components
  are highly performant. Most notably our use of [Kafka](https://kafka.apache.org/), the [Monasca persister](/components/persister/) and our use of
  a dedicated [metrics DB](/components/metrics_db/).
- Our system can dynamically handle infrastructure changes. There is no need to pre-register metrics before submitting,
[alarm definitions](https://github.com/openstack/monasca-api/blob/master/docs/monasca-api-spec.md#alarm-definitions-and-alarms) provide dynamic alarm
creation based on the metrics being received and dimensions in our [metrics](/components/metrics) provide a rich way to identify components and infrastructure.
- Monasca is Multi-tenant and authenticated. Metrics are submitted and authenticated using [Keystone](http://docs.openstack.org/developer/keystone/)
  and stored associated with a tenant ID. This enables not only Operator monitoring but also Monitoring as a Service use cases.
- The [Monasca agent](/components/agent/) is highly extensible with out of the box support for monitoring of many services as well as supporting
  existing Nagios checks and statsd metrics.
- Our system is fully open source under the Apache license.
- [Notifications](/components/notifications/) can be sent using a variety of methods including email, pagerduty and generic webhooks for integrating
  with other systems.
- [Thresholding on alarming](/components/alarms/) on metrics is done real-time with compound alarms described using a simple expressive grammar
  composed of alarm sub-expressions and logical operators.
- The overall architecture is a [microservices](http://martinfowler.com/articles/microservices.html) [message bus](http://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageBus.html) architecture that allows for [easy extensibility](/root/coming-soon).
