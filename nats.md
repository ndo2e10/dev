Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: node 12x, npm 6x

## NATS

```
curl -L https://github.com/nats-io/nats-server/releases/download/v2.1.0/nats-server-v2.1.0-linux-amd64.zip -o ~/nats-server.zip
sudo apt install unzip
unzip ~/nats-server.zip -d ~/nats-server
```

## Useful links
* https://medium.com/capital-one-tech/lightweight-cloud-native-messaging-with-nats-ad730ca2becf
* https://nats-io.github.io/docs/nats_protocol/nats-protocol.html
* https://docs.nestjs.com/microservices/basics
