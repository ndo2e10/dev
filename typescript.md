Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: node 12x, npm 6x

* get typescript with npm

```
$ sudo npm -g i typescript # will provide tsc
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
