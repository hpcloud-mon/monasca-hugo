+++
Categories = ["Debugging", "Operations"]
date = "2015-08-14T16:42:17-06:00"
title = "Monitoring of Monitoring"

+++

Monasca itself needs to be monitored and is fully capable of monitoring itself. <!--more--> In non-production installations this can be done by the agent running on the Monasca boxes reporting back to the Monasca API. For production installations I recommend that the agent running on the Monasca nodes report to another installation of Monasca possibly a single vm 'mini-mon' which is itself monitored by the primary installation, this avoids dependency loops.

As components of Monasca are developed metrics for the monitoring of that component need to be added as well as alarm definitions and finally default graphs to view the metrics. The most basic metrics are used in simple up/down alarms and more advanced used for thresholds and graphs aiding in predictive failure and capacity planning.

Here are the MoM alarms broken down by component, the exact alarms can be found at https://github.com/hpcloud-mon/ansible-monasca-default-alarms/blob/master/tasks/monasca.yml

Component | Alarm
----------|-------
zookeeper | pid check, average latency, zookeeper connections_count
kafka | pid check, consumer lag
mysql | pid check, slow queries
notification | pid check, config db time, email time
thresh/storm | pid check of nimbus, supervisor and workers
Agent | emit time, collection time
Persister | For the Java version a healthcheck on the admin url
API | For the Java version a healthcheck on the admin url

