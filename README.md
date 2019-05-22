package-deps
=================

This is deprecated, as it was designed for how NPM used to download packages.
Unless you have a really version of NPM, don't use this.

Examine a package.json's dependencies and find all sub-depdendcies.

## Installation

    npm install package-deps

## Example

    var packageDeps = require('package-deps');
    var deps = packageDeps.findAll('./package.json');

    var util = require('util');
    console.log(util.inspect(deps, {colors:true, depth: null}));

The above has the following output:

    { dependcies:
       { async: '0.2.9',
         debug: '0.7.4',
         have: '0.2.3',
         lodash: '2.4.1' },
      packageJson: '/Users/edmond/src/package-deps/package.json',
      async: { packageJson: '/Users/edmond/src/package-deps/node_modules/async/package.json' },
      debug:
       { dependcies: {},
         packageJson: '/Users/edmond/src/package-deps/node_modules/debug/package.json' },
      have: { packageJson: '/Users/edmond/src/package-deps/node_modules/have/package.json' },
      lodash: { packageJson: '/Users/edmond/src/package-deps/node_modules/lodash/package.json' } }

### findAll(pathToPackageJson [, depth])

Finds all dependancies for a path to a package.json. It will read the
dependencies and find all the sub-dependencies.

#### Params: 

* **String** *pathToPackageJson* Path to the package.json file.
* **Number** *\[depth\]* How far down the dependency tree to go. Optional. If not defined, all dependencies are found. If 1, only the top-level dependencies are found.

#### Return:

* **Object** An object describing the dependencies.

## LICENSE
The MIT License (MIT)

Copyright (c) 2013 Edmond Meinfelder

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

