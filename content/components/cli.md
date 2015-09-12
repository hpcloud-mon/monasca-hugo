+++
Categories = ["components"]
date = "2015-08-19T15:19:37-06:00"
title = "cli"
weight = 10

+++

[python-monascaclient](https://github.com/stackforge/python-monascaclient) is the Monasca CLI built in the same style as other OpenStack CLI's. <!--more-->
The CLI provides commands for a full range of [Monasca API](/components/api/) methods.

Like most OpenStack CLI's all that is needed to run it a keystone user, password and endpoint. These can be specified as arguments or using the standard
environment variables.

In addition it can be used as a python module to provide a standard python interface for interacting with the [Monasca API](/components/api/).
It is used in this way by the [Monasca Agent](/components/agent/) and so is installed wherever the agent is installed.

Run the CLI with `-h` or refer to the [README](https://github.com/stackforge/python-monascaclient/blob/master/README.rst) for more
details on using the Monasca CLI.
