# Vnscoin JavaScript API

[![Join the chat at https://gitter.im/ethereum/web3.js](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ethereum/web3.js?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This is the Vnscoin compatible [JavaScript API](https://github.com/AMTcommunity/go-vnscoin/wiki/JavaScript-API)
which implements the [Generic JSON RPC](https://github.com/AMTcommunity/go-vnscoin/wiki/JSON-RPC) spec. It's available on npm as a node module, for Bower and component as embeddable scripts, and as a meteor.js package.

[![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![dependency status][dep-image]][dep-url] [![dev dependency status][dep-dev-image]][dep-dev-url] [![Coverage Status][coveralls-image]][coveralls-url] [![Stories in Ready][waffle-image]][waffle-url]

<!-- [![browser support](https://ci.testling.com/ethereum/ethereum.js.png)](https://ci.testling.com/ethereum/ethereum.js) -->

You need to run a local Ethereum node to use this library.

[Documentation](https://github.com/AMTcommunity/go-vnscoin/wiki/JavaScript-API)

## Table of Contents

- [Installation](#installation)
  - [Node.js](#nodejs)
  - [Yarn](#yarn)
  - [Meteor.js](#meteorjs)
  - [As a Browser module](#as-a-browser-module)
- [Usage](#usage)
  - [Migration from 0.13.0 to 0.14.0](#migration-from-0130-to-0140)
- [Contribute!](#contribute)
  - [Requirements](#requirements)
  - [Building (gulp)](#building-gulp)
  - [Testing (mocha)](#testing-mocha)
  - [Community](#community)
  - [Other implementations](#other-implementations)
- [License](#license)

## Installation

### Node.js

```bash
npm install vns-web3
```

### Yarn

```bash
yarn add vns-web3
```


## Usage

Use the `web3` object directly from the global namespace:

```js
console.log(web3); // {vns: .., shh: ...} // It's here!
```

Set a provider (`HttpProvider`):

```js
if (typeof web3 !== 'undefined') {
  web3 = new Web3(web3.currentProvider);
} else {
  // Set the provider you want from Web3.providers
  web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8585"));
}
```

Set a provider (`HttpProvider` using [HTTP Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication)):

```js
web3.setProvider(new web3.providers.HttpProvider('http://' + BasicAuthUsername + ':' + BasicAuthPassword + '@localhost:8585'));
```

There you go, now you can use it:

```js
var coinbase = web3.vns.coinbase;
var balance = web3.vns.getBalance(coinbase);
```

You can find more examples in the [`example`](https://github.com/ethereum/web3.js/tree/master/example) directory.


## Contribute!

### Requirements

* Node.js
* npm

```bash
# On Linux:
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
sudo apt-get install nodejs-legacy
```

### Building (gulp)

```bash
npm run-script build
```


### Testing (mocha)

```bash
npm test
```

### Community
 - [Gitter](https://gitter.im/ethereum/web3.js?source=orgpage)
 - [Forum](https://forum.ethereum.org/categories/ethereum-js)


## License

[LGPL-3.0+](LICENSE.md) © 2015 Contributors


