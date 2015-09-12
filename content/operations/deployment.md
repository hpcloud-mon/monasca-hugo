+++
weight = 4
Categories = ['operations']
date = "2015-08-18T17:09:52-06:00"
title = "deployment"

+++

Monasca is a system built for large scale deployments.<!--more--> One side effect of this is there are many components in the system each of which is an
installation in and of itself. The end result of this is that I highly recommend you use a configuration management system to install Monasca.

The HP Monasca team has published a set of [Ansible](http://www.ansible.com/home) roles that can be used to install and configure Monasca on
Debian/Ubuntu based machines. These roles all are in repos that start with 'ansible-' and are available on github under the
[hpcloud-mon organization](https://github.com/hpcloud-mon?utf8=%E2%9C%93&query=ansible-). These roles are used in the [Monasca Vagrant](/dev/vagrant/)
development environment but are also used internally at HP for full HA installations of Monasca.

In addition to the Ansible roles a [Puppet](https://puppetlabs.com/) module is maintained by the Monasca community in the
[puppet-monasca](https://github.com/openstack/puppet-monasca) git repository.
