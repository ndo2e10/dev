* setting up

```
$ mkdir ubuntu
$ cd ubuntu
$ vagrant init hashicorp/precise64
$ vagrant up
$ vagrant ssh
$ vagrant halt #suspend
```

* provisioning bootstrap.sh (same dir as VagrantFile)

```
apt-get update & apt-get upgrade
apt-get install nodejs -y
```


