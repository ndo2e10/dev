Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: node 12x, npm 6x

## NATS

```
# download
curl -L https://github.com/nats-io/nats-server/releases/download/v2.1.0/nats-server-v2.1.0-linux-amd64.zip -o ~/nats-server.zip

# extract
sudo apt install unzip
unzip ~/nats-server.zip -d ~/nats-server
```

* update VagrantFile for port fowarding (vargrant reload after modification)

```
config.vm.network :forwarded_port, guest: 4222, host: 4223
```

* start nats server 

```
# start default port 4222
./nats-server & 
```

### Play with telnet

NATS is an incredibly fast, open source messaging system built on a simple, yet powerful, core. The server uses a text-based protocol, so while there are a number of language-specific client libraries, you can literally telnet into a NATS server and send and receive messages. NATS is designed to be always-on, connected and ready to accept commands.

* first terminal, connect and subscribe to subject=test, internal id=0

```
telnet localhost 4222
sub test 0
+OK
```

* second terminal, connect and publish to subject=test, content length=1, payload=A

```
telnet localhost 4222
pub test 1
A
+OK
```

subscriber will receive: 

```
MSG test 0 1
A
```

## Javascript client

```
mkdir /vagrant/nats-app
npm init
npm i nats -S
vim index.js
```

* index.js

``` 
const NATS = require('nats');
const nats = NATS.connect();
 
// simple subscriber
nats.subscribe('test', function(msg) {
  console.log('Received a message: ' + msg);
});
```

* run: node index.js  
* connect to nats using telnet
  * publish to subject=test, content length=5, payload=Hello
  * publish to subject=test, content length=5, payload=World


## Useful links
* https://medium.com/capital-one-tech/lightweight-cloud-native-messaging-with-nats-ad730ca2becf
* https://nats-io.github.io/docs/nats_protocol/nats-protocol.html
* https://github.com/nats-io/nats.js
* https://docs.nestjs.com/microservices/basics
