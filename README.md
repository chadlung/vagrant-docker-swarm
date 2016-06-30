Vagrant Docker Swarm
====================

Scripts to quickly spin up a three node (1 manager, 2 workers) [Docker Swarm](https://www.docker.com/products/docker-swarm) for development using Vagrant.

To get started from a terminal:

```
$ git clone https://github.com/chadlung/vagrant-docker-swarm.git
$ cd vagrant-docker-swarm
$ vagrant plugin install vagrant-vbguest
$ vagrant up
```

Once the three VMs are up and running you can log into **manager1** by running:

```
$ vagrant ssh manager1
```

Log into the workers just as easily:

```
$ vagrant ssh worker1
```

Or:

```
$ vagrant ssh worker2
```

Follow my [blog article here](http://www.giantflyingsaucer.com/blog/?p=5923) to learn how to get the Docker Swarm running.

The VMs will be running with IPs:
* manager1: 192.168.99.100
* worker1: 192.168.99.101
* worker2: 192.168.99.102
