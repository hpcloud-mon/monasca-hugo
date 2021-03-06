+++
weight = 2
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "api"
categories = [ "Components" ]
+++

The [Monasca API](https://github.com/openstack/monasca-api/) is built on a first-class RESTful API that provides authentication and multi-tenancy. <!--more--> Monasca integrates with the OpenStack Keystone Identity service. 

Monasca supports the following main resources in the API:

- GET /v2.0/versions: Supplies operations for accessing information about supported versions of the API.
- GET, POST /v2.0/metrics: Allows metrics to be created and queried.
- GET /v2.0/metrics/names: Operations for accessing names of metrics.
- GET /v2.0/metrics/measurements: Operations for accessing measurements of metrics.
- GET /v2.0/metrics/statistics: Operations for calculating statistics of metrics
- GET, POST, PUT, PATH, DELETE /v2.0/alarm-definitions: Operations for working with alarm definitions.
- GET, PUT, DELETE /v2.0/alarms: Operations for working with alarms.
- GET /v2.0/alarms/state-history: List alarm state history for alarms.
- GET, POST, PUT, DELETE /v2.0/notification-methods: Operations for working with notification methods.

Refer to the [full API spec](https://github.com/openstack/monasca-api/blob/master/docs/monasca-api-spec.md) for more info.
