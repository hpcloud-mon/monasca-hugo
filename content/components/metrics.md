+++
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "metrics"
categories = [ "components" ]
+++

Provides an API for real-time storage and retrieval of metrics and statistics. <!--more--> The main features of metrics are as follows:

- Storage and retrieval of metrics.
- Push-based, streaming of metrics. Monasca support pushing metrics to the API, and does not support pull-based metrics.
- Query statistics about metrics, such as average, min, max, sum and count, over time ranges and periods.
- Multi-dimensional representation based on dimensions, (key, value) pairs to that data can be easily sliced and diced.
- Millisecond resolution.
- Meta data associated with metrics can be used to provide additional about metrics such as http status codes and error messages. For example, if Nagious plugins are run by the Monasca Agent, the resulting error description can be sent as meta data with the metric. 
- Long data retention periods of metrics in their original fidelity, without lossy compression and rollups.

##### Anatomy of a metric

A metric is a simple, concise, multi-dimensional and flexible description that consists of the following fields:

- name: A user-friendly name of the metric as a string.
- dimensions: A dictionary of user-defined (key, value) pairs that are used to uniquely identify a metric and can be used to filter and slice-and-dice metrics.
- timestamp: Time in milliseconds from the epoch.
- value: A float.
- value_meta: An optional dictionary of user-defined (key, value) pairs that can be used to describe a measurement. Value_meta is typically used to decribe status codes and error messages.

##### Example

```
    POST /v2.0/metrics
    {
	name: cpu.user_perc,
	dimensions: {
		hostname: hostname.domain.com,
		region: uswest,
		zone: 1,
		service: compute
	}
	timestamp: 0, /* milliseconds */
	value: 0.0,
	value_meta: {
		status_code: 400,
		msg: Internal server error
	}
    }
```

