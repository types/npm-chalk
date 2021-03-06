# Typed Chalk

[![Greenkeeper badge](https://badges.greenkeeper.io/types/npm-chalk.svg)](https://greenkeeper.io/)
[![Build Status](https://travis-ci.org/types/npm-chalk.svg?branch=master)](https://travis-ci.org/types/npm-chalk)

The type definition for [chalk](https://github.com/chalk/chalk).

## Installation
```sh
typings install --save chalk
```

## Usage

```ts
import chalk = require('chalk');

let val: string;

// combine styled and normal strings
val = chalk.blue('Hello') + 'World' + chalk.red('!');

// compose multiple styles using the chainable API
val = chalk.blue.bgRed.bold('Hello world!');

// pass in multiple arguments
val = chalk.blue('Hello', 'World!', 'Foo', 'bar', 'biz', 'baz');

// nest styles
val = chalk.red('Hello', chalk.underline.bgBlue('world') + '!');

// nest styles of the same type even (color, underline, background)
val = chalk.green(
    'I am a green line ' +
    chalk.blue.underline.bold('with a blue substring') +
    ' that becomes green again!'
);

// ES2015 template literal
const systemStats = `
CPU: ${chalk.red('90%')}
RAM: ${chalk.green('40%')}
DISK: ${chalk.yellow('70%')}
`;

// create a reusable instance
let ctx: chalk.Chalk;
ctx = new chalk.constructor({enabled: false});
ctx = new chalk.constructor();

// use interfaces
function sayHello(style: chalk.Style): void {
  console.log(style('Hello World'));
}
```

## Contributing
You can run the tests by running `npm run build` and then `npm run test`.


## License

MIT
