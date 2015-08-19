+++
Categories = ["development"]
date = "2015-08-19T10:20:28-06:00"
title = "Testing Monasca"
weight = 10

+++

As part of OpenStack the primary testing for Monasca is done using the [OpenStack testing](https://wiki.openstack.org/wiki/Testing). <!--more-->Monasca code
runs through the standard [OpenStack CI](http://docs.openstack.org/infra/system-config/). Additionally work to integrate
[Monasca into tempest](https://github.com/hpcloud-mon/monasca-tempest) is ongoing.

Some additional test scripts used in our test environment including an experimental CI system is available in the
[Monasca CI repository](https://github.com/hpcloud-mon/monasca-ci).
