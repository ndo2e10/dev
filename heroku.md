Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: node 12x, npm 6x, nestjs/cli, heroku cli, git

```
$ nest new croissant-app
$ cd /vagrant/croissantApp
$ npm run start
```

add to VagrantFile

```
config.vm.network :forwarded_port, guest: 3000, host: 3001
```

reload

```
$ vagrant reload
```

test nestjs endpoint (host machine): ```http://localhost:3001```

create Procfilefile

```
web: npm run start:prod
```

deploy to heroku

```
$ heroku login -i
$ git init
$ heroku create
$ git add . #don't forget .gitignore file with dist and node_modules
$ git commit -m "Croissant-App"
$ git push heroku master #push and deploy
$ heroku logs -n 200 #view logs

```