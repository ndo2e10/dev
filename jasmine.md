Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: node 12x, npm 6x

* also have [a look at typescript file](typescript.md)


## Sample app

* bootstrap and install as dev dependencies
  * jasmine as test framework
  * nyc for test coverage
  * ts-node for running typescript on node directly
  * typescript
  
```
mkdir /vagrant/sample-app
npm init
npm i jasmine nyc ts-node typescript -D
npm i @types/jasmine -D
```

* update package.json file with test script

```
"scripts": {
  "test": "ts-node node_modules/jasmine/bin/jasmine --config=jasmine.json",
  "coverage": "nyc -r text -e .ts -x \"tests/*.test.ts\" npm run test"
}
```

* jasmine.json


```
"spec_dir": "tests",
"spec_files": ["**/*[tT]est.ts"]
```

* sample test

```
describe('calculate', function() {
  it('add', function() {
    let result = Calculator.Sum(5, 2);
    expect(result).toBe(7);
  });
});
```


* test / coverage

```
npm t
npm run coverage
```
