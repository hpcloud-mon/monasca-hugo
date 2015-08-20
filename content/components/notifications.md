+++
weight = 5
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "notifications"
categories = [ "Components" ]
+++

Notifications can be sent when alarm state transition occurs. <!--more--> Monasca supports an integrated
[notification engine](https://github.com/stackforge/monasca-notification) that can send various notification types.
[Alarm Definitions](https://github.com/stackforge/monasca-api/blob/master/docs/monasca-api-spec.md#alarm-definitions-and-alarms) can be associated
with [notification methods](https://github.com/stackforge/monasca-api/blob/master/docs/monasca-api-spec.md#notification-methods) for
transitions to the states, OK, Alarm or Undetermined.

Notification methods of the following types are supported:

- Email
- PagerDuty
- Webhooks
