StackStorm ST2 JavaScript bindings [![Build Status][travis-image]][travis-url]
==============================================================================

Officially supported node.js\browserify client library for using ST2 APIs.

The library (and the whole API, to be fair) is in **Alpha**, so incompatible changes should be expected.

## Installation

The library is distributed through the npm. To install it, run:

    npm install st2client

## Usage

Depending on the environment, you need to either require it (node\browserify)

    var api = require('st2client')();

or add a script tag to the head of your `index.html` and access it through the global variable

    <script src="node_modules/st2client/dist/st2client.js"></script>
    <script>
      ...
      var api = st2client(config);
      ...
    </script>

In both cases, `st2client` is a factory that takes `config` object as an argument and returns an `api` object with a number of entities (`actions`, `actionExecutions`, `rules`, ...) each having a set of methods (`list()`, `get()`, `create()`, ...). Method returns an A+ compliant promise or throws an error if it can't make a request due to insufficient data (i.e. `id` in `api.actions.get(id)` is undefined).

## Documentation
[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/StackStorm/st2?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Please refer to [StackStorm Docs](http://docs.stackstorm.com).

## Hacking

To build it manually, clone the project, install dependencies and then run `gulp`

    npm install -g gulp
    npm install
    gulp

You can also launch gulp in a watch state so it would lint and recompile browserify version every time it will detect the change.

Integration tests require `st2` to be present. To set up dev environment and run StackStorm from sources, follow [these instructions](docs/source/install/sources.rst).

## Copyright, License, and Contributors Agreement

Copyright 2014 StackStorm, Inc.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work except in compliance with the License. You may obtain a copy of the License in the [LICENSE](LICENSE) file, or at:

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

By contributing you agree that these contributions are your own (or approved by your employer) and you grant a full, complete, irrevocable copyright license to all users and developers of the project, present and future, pursuant to the license of the project.

[travis-url]: https://travis-ci.org/stackstorm/st2client.js
[travis-image]: https://travis-ci.org/StackStorm/st2client.js.svg