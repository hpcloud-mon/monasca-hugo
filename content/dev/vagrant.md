+++
Categories = ["development"]
date = "2015-08-19T10:20:22-06:00"
title = "Vagrant Development Environment"
weight = 10

+++
The Monasca team has built a [Vagrant](https://www.vagrantup.com/) based development environment which is especially helpful for any development
on the server stack of Monasca.<!--more--> This environment and extensive instructions on running it are found at the github repo
[monasca-vagrant](https://github.com/openstack/monasca-vagrant).

The environment installs the latest Monasca code and all dependencies into two VMs. You can then turn off components as needed for development. There are some
limitations to this environment, most notably it is a non-HA environment and initial downloads can take awhile.

If you are simply looking for an API endpoint and have no need to develop on the server stack of Monasca another options is to run the
[Monasca Demo](/root/demo/) and use its api. This should be simpler to start up and experience less churn with the normal development process.
