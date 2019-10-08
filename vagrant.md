* setting up

```
$ mkdir ubuntu
$ cd ubuntu
$ vagrant init ubuntu/bionic64
$ vagrant up
$ vagrant ssh
$ vagrant halt #suspend
```

* provisioning 
** VagrantFile

```
config.vm.provision :shell, path: "bootstrap.sh"
```

* bootstrap.sh (same dir as VagrantFile)

```
#!/usr/bin/env bash

sudo apt update
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install -y nodejs
echo "node version: `node --version`, npm version: `npm --version`"
npm -g i @nestjs/cli
```

* re-provision (if vm already runnint)

```
vagrant reload --provision
```


