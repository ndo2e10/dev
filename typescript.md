Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: node 12x, npm 6x

## Typescript

* get typescript with npm

```
$ sudo npm -g i typescript # will provide tsc
```

We will use vim as main editor so use a decent .vimrc file:

https://vim.fandom.com/wiki/Example_vimrc

also add javascript highlight for typescript files

```
autocmd BufNewFile,BufRead *.ts set syntax=javascript
```

## Sample app

```
mkdir /vagrant/nats-app
npm init
vim hello.ts
```

* hello.ts

```
interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person: Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

let user = { firstName: "Nuno", lastName: "X" };
console.log(greeter(user));
```

* compile and run

```
tsc hello.ts
node hello.js #output: Hello, Nuno X
```
