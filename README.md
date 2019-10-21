# dev


![nodejs version](https://img.shields.io/badge/node-%3E%3D%2012-success)

## GitHub Pages

(out-of-the-box feature on github)
* https://<username>.github.io/<repo>/

Markdown files are dynamically wrapped as HTML pages and links are converted:

* [readme](README.md)
* [vagrant doc](vagrant.md)
* [heroku doc](heroku.md)
* [typescript doc](typescript.md)
* [nats doc](nats.md)


## read.html

read.html is a static html page used to render this repository's markdown content.

It uses zero-md (loaded async) to render raw markdown files, name of content is passed with query param **md**.

This repository is also auto-deployed to **zeit now** on every commit.

Following markdown files can be viewed as static html files: 

* https://dev.ndo2e10.now.sh/read.html
* https://dev.ndo2e10.now.sh/read.html?md=vagrant
* https://dev.ndo2e10.now.sh/read.html?md=heroku
* https://dev.ndo2e10.now.sh/read.html?md=typescript
* https://dev.ndo2e10.now.sh/read.html?md=nats

## to-read (links)

https://v8.dev/features/modules
