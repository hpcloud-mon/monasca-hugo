+++
Categories = ["development"]
date = "2015-08-19T10:20:28-06:00"
title = "Testing Monasca"
weight = 10

+++

As part of OpenStack the primary testing for Monasca is done using the [OpenStack testing](https://wiki.openstack.org/wiki/Testing) tools and process.
<!--more-->Monasca code runs through the standard [OpenStack CI](http://docs.openstack.org/infra/system-config/) using the [Monasca DevStack Plugin](https://github.com/openstack/monasca-api/tree/master/devstack) and [Monasca Tempest Tests](https://github.com/openstack/monasca-api/tree/master/monasca_tempest_tests).
