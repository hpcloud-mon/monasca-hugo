+++
Categories = ['Debugging', 'Operations']
date = "2015-08-14T16:27:56-06:00"
title = "Log and Configuration Locations"
+++

**Monasca Components**

All monasca components have their configuration in `/etc/monasca` and their log files in `/var/log/monasca`
<!--more-->

- /var/log/monasca/agent/collector.log
- /var/log/monasca/agent/statsd.log
- /var/log/monasca/agent/supervisord.log
- /var/log/monasca/agent/forwarder.log
- /var/log/monasca/api/monasca-api.log
- /var/log/monasca/api/request.log
- /var/log/monasca/notification/notification.log
- /var/log/monasca/persister/monasca-persister.log

**3rd Party Monasca Dependencies**

The 3rd party Monasca dependencies can put there logs where ever they desire but here are the common locations:

- /var/log/influxdb/influxd.log
- /var/log/kafka/controller.log
- /var/log/kafka/server.log
- /var/log/kafka/state-change.log
- /var/log/mysql/error.log
- /var/log/storm/nimbus.log
- /var/log/storm/supervisor.log
- /var/log/zookeeper/zookeeper.log
