title: Getting started with open source
output: index.html
theme: theme
controls: false

-- intro

# Getting started with open source

---

## Topics

- Git & Github
- Branches, Pull Request
- What is NodeJS
- NPM packages and package.json
- Creating a node project
- A NodeJS webserver
- Testing
- Continuous Integration (CI)

--

## Git

> A distributed version control system

<img src="img/git-logo.png" alt="Git" style="height: 300px; margin: 0 auto; display: block;">

--

## GitHub

A platform for collaborating on source code.

[<img alt="Codercat" src="img/codercat.jpg" style="height: 400px;">](https://octodex.github.com/) [<img alt="Mountietocat" src="img/mountietocat.png" style="height: 400px;">](https://octodex.github.com/)

--

## Branches, Pull Request

[<img src="img/branches_git.png" alt="Git branches" style="height: 500px; margin: 0 auto; display: block;">](https://git-scm.com/)

--

## What is NodeJS

> A JavaScript runtime to build scalable network applications

[<img src="img/node-js-logo.png" alt="NodeJS logo" style="height: 350px; margin: 0 auto; display: block;">](https://nodejs.org/)

--

## The [__N__ode __P__ackage __M__anager](https://npmjs.org)

- currently hosts ~ 1m modules
- easy to use (`npm install <package>`)
- easy to publish (`npm publish`)
- use it with anything (folders, tarballs, git repositories)

### [CommonJS](http://www.commonjs.org/)

- Attempt for JavaScript API standardization

---

## CommonJS modules

Provides global `module`, `exports` and `require()` to define this files API

```js
// module1.js
exports.hello = 'World';
// or
module.exports = {
  hello: 'World'
}
```

Using the module

```js
// main.js
var mod1 = require('./module1');

console.log(mod1.hello); // -> World
```

--

## package.json

CommonJS specification for describing JavaScript packages

```js
{
  "name": "nodeschool",
  "version": "0.1.0",
  "author": "Nodeschool <people@nodeschool.com>",
  "description": "NodeJS FTW!",
  "scripts": {
    "test": "mocha test",
    "start": "node lib/start.js"
  },
  "main": "./lib/main.js",
  "repository": {
    "type": "git", "url": "https://github.com/yycjs/node-up"
  },
  "dependencies": { "somePackage": "^1.0.0" },
  "devDependencies": { "some-dev-only-package":  "^0.2.0" },
  "license": "MIT"
}
```

--

## A NodeJS webserver

```javascript
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

--

## Testing

> Split functionality into contained units. Ideally each function should perform one __unit__ of work.

- Testing frameworks: [Mocha](https://mochajs.org/), [Jest](https://jestjs.io/), [Jasmine](https://jasmine.github.io/), [Ava](https://github.com/avajs/ava)
- Code quality tools
  - [ESLint](https://eslint.org/)
  - [Istanbul](https://github.com/istanbuljs) (code coverage)
  - [Codeclimate](https://codeclimate.com/)

--

## Continuous Integration (CI)

- Use source control management system (SCM) for builds
- Run reports, tests, deploy or other tools on each SCM change
- Popular open source CI servers:
	- [Jenkins](http://jenkins-ci.org/): Probably most popular CI server, formerly Hudson
	- [CruiseControl](http://cruisecontrol.sourceforge.net/): CI framework initially by Thoughtworks
- Hosted CI services
	- [TravisCI](http://travis-ci.org): Distributed build platform for the open source community
	- [Codeship](https://www.codeship.io/): Build and deploy service
	- [Circle CI](https://circleci.com/)
