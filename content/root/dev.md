+++
weight = 6
Categories = ['overview', 'development']
date = "2015-08-18T17:04:58-06:00"
title = "dev"

+++
Monasca is an active [OpenStack](https://www.openstack.org/) project and welcomes new developers.<!--more-->

#### OpenStack Community

Monasca was formally accepted as an official OpenStack project in November, 2015 during the [OpenStack Governance Review for Monasca](https://review.openstack.org/#/c/213183/) and follows the OpenStack [contribution guidelines](https://wiki.openstack.org/wiki/How_To_Contribute) and [code standards](http://docs.openstack.org/developer/hacking/).

The Monasca project has a [launchpad site](https://launchpad.net/monasca) which is primarily used for bug tracking and blueprints.
The project mailing list is also hosted on launchpad, at the [Monasca Launchpad Team](https://launchpad.net/~monasca).

Monasca hosts weekly meetings in IRC as well as other venues, such as mid-cycle meetups and OpenStack Summits.
Details on the team meetings can be found at [Monasca Weekly Meeting](http://eavesdrop.openstack.org/#Monasca_Team_Meeting) and the [Monasca Wiki](https://wiki.openstack.org/wiki/Meetings/Monasca).

#### Code Contributions

Monasca is hosted in Github by the [Github OpenStack Organization](https://github.com/openstack?query=monasca).

All code is submitted via the [OpenStack Gerrit Review System](https://review.openstack.org/#/q/status:open+monasca,n,z) and is under gated tests that include a battery of unit and functional tests using the [Monasca DevStack Plugin](https://github.com/openstack/monasca-api/tree/master/devstack) and [Monasca Tempest Tests](https://github.com/openstack/monasca-api/tree/master/monasca_tempest_tests) .

Currently, the [Monasca Vagrant](/dev/vagrant/) environment is the primary development environment for Monasca.
The [Monasca DevStack Plugin](https://github.com/openstack/monasca-api/tree/master/devstack) environment is also used as a development environment.
More information on testing Monasca can be found at the [testing page](/dev/testing/).
