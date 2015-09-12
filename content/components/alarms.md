+++
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "alarms"
categories = [ "components" ]

+++

Included as part of Monasca is a real-time in-memory streaming thresholding engine capable of processing hundreds of thousands of metrics. <!--more--> 
The [threshold engine](https://github.com/stackforge/monasca-thresh) is based on [Apache Storm](http://storm.apache.org/) and written in Java.

As metrics come into our system they are read from Kafka by the threshold engine then evaluated against any configured
[alarm definitions](https://github.com/stackforge/monasca-api/blob/master/docs/monasca-api-spec.md#alarm-definitions-and-alarms). Alarms are created
automatically, evaluated and sent to the proper state as metrics flow through the system. When any alarm changes state an alarm-state-transition message
is added to Kafka so other processes can consume this event.
