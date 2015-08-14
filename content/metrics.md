+++
weight = 3
date = "2015-08-07T18:32:00-06:00"
draft = false
title = "metrics"
+++

Provides an API for real-time storage and retrieval of metrics and statistics. <!--more--> The main features of metrics are as follows:

  1. Storage and retrieval of metrics.
  2. Push-based, streaming of metrics. Monasca support pushing metrics to the API, and does not support pull-based metrics.
  3. Query statistics about metrics, such as average, min, max, sum and count, over time ranges and periods.
  4. Multi-dimensional representation based on dimensions, (key, value) pairs to that data can be easily sliced and diced.
  5. Millisecond resolution.
  6. Meta data associated with metrics can be used to provide additional about metrics such as http status codes and error messages. For example, if Nagious plugins are run by the Monasca Agent, the resulting error description can be sent as meta data with the metric. 
  7. Long data retention periods of metrics in their original fidelity, without lossy compression and rollups.

##### Anatomy of a metric

A metric is a simple, concise, multi-dimensional and flexible description that consists of the following fields:

  1. name: A user-friendly name of the metric as a string.
  2. dimensions: A dictionary of user-defined (key, value) pairs that are used to uniquely identify a metric and can be used to filter and slice-and-dice metrics.
  3. timestamp: Time in milliseconds from the epoch.
  4. value: A float.
  5. value_meta: An optional dictionary of user-defined (key, value) pairs that can be used to describe a measurement. Value_meta is typically used to decribe status codes and error messages.

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

