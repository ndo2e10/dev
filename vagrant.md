* setting up

```
$ mkdir ubuntu
$ cd ubuntu
$ vagrant init ubuntu/bionic64 #initialize box, binaries under .vagrant.d/boxes
$ vagrant up #start vm
$ vagrant ssh #connect
$ vagrant suspend #halt #destroy
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
# get nodejs v12 packages
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash - 
sudo apt install -y nodejs
echo "node version: `node --version`, npm version: `npm --version`"
sudo npm -g i @nestjs/cli
sudo snap install --classic heroku
```

* re-provision (if vm already running)

```
vagrant reload --provision
```


