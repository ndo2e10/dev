Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: node 12x, npm 6x

* also have [a look at typescript file](typescript.md)


## Sample app

* bootstrap and install as dev dependencies
  * jasmine as test framework
  * nyc for test coverage
  * ts-node for running typescript on node directly
  * typescript
  * jasmine types
  
```
mkdir /vagrant/sample-app
npm init -y
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

* sample test calculator.test.ts

```
import {Calculator} from '../src/calculator';

describe('calculate', function() {
  it('add', function() {
    let result = Calculator.sum(5, 2);
    expect(result).toBe(7);
  });
});
```

* calculator.ts

```
export class Calcuator {
  static sum(a: number, b: number) : number {
    return a + b;
  }
}

```

* test / coverage

```
npm t
npm run coverage
```
