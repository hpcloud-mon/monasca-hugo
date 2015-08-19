+++
Categories = ["overview"]
date = "2015-08-19T10:17:37-06:00"
title = "demo"
weight = 10

+++

The primary demo for environment for Monasca is a Docker Image. <!--more--> To avoid setting all of Monasca up just to investigate it I have created
a [Docker](https://www.docker.com/) [demo image](https://hub.docker.com/r/monasca/demo/) that contains all of the Monasca components.

This image can be run via [kitematic](https://kitematic.com/) or directly in a Docker installation. If running with Docker simply run

    docker run -d -p 80:80 -p 8080:8080 -p 5000:5000 --name monasca monasca/demo

and the image will download and start. The demo has a keystone user `mini-mon` with the password `password`. The Monasca horizon plugin is available
on port 80, the [Monasca API](/components/api/) on port 8080 and the embedded keystone on port 5000. Additionally if you shell into the environment
a set of env variables is available at `/setup/env.sh` so you can simple source this file and begin using the [Monasca CLI](/components/cli).

#### Alternatives
Besides the Docker demo the Monasca uses a [Vagrant](https://www.vagrantup.com/) environment for development and this can be used as an alternative
demo environment. It is a bit more involved to setup but works well, more information at the [development with vagrant page](/dev/vagrant/).
