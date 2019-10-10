Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: node 12x, npm 6x, nestjs/cli, heroku cli, git

```
$ nest new croissant-app
$ cd /vagrant/croissantApp
$ heroku login -i
$ heroku create
$ npm run start
```

add to VagrantFile

```
config.vm.network :forwarded_port, guest: 3000, host: 3001
```

reload


$ vagrant reload
```
