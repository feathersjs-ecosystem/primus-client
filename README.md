# @feathersjs/primus-client


> __Important:__ The code for this module has been moved into the main Feathers repository at [feathersjs/feathers](https://github.com/feathersjs/feathers) ([package direct link](https://github.com/feathersjs/feathers/tree/master/packages/primus-client)). Please open issues and pull requests there. No changes in your existing Feathers applications are necessary.

[![Build Status](https://travis-ci.org/feathersjs/primus-client.png?branch=master)](https://travis-ci.org/feathersjs/primus-client)

Client services for Primus and feathers-primus

## Installation

```
npm install @feathersjs/primus-client --save
```

Quick usage:

```js
const feathers = require('@feathersjs/feathers');
const primus = require('@feathersjs/primus-client');
const socket = new Primus('http://api.my-feathers-server.com');

const app = feathers();

app.configure(primus(socket));

// Receive real-time events through Primus
app.service('messages')
  .on('created', message => console.log('New message created', message));

// Call the `messages` service
app.service('messages').create({
  text: 'A message from a REST client'
});
```

## Documentation

Please refer to the [@feathersjs/primus-client documentation](https://docs.feathersjs.com/api/client/primus.html) for more details.

## License

Copyright (c) 2018

Licensed under the [MIT license](LICENSE).
