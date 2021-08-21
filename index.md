# 📦  `init-package-json`

A node module to get your node module started.

[![Build Status](https://secure.travis-ci.org/npm/init-package-json.svg)](http://travis-ci.org/npm/init-package-json)

## Usage

### Command Line

```bash
npm-init
```

### Javascript 

```javascript
var init = require('init-package-json')
var path = require('path')

/** 
 * Path to a PromZard module. If it's not found, one will be provided for you.
 */
var initFile = path.resolve(process.env.HOME, '.npm-init')

var dir = process.cwd()

/**
 * Optional extra stuff that gets put into the PromZard module's context.
 * In npm, this is the resolved config object.  Exposed as `config`:
 */
var configData = { some: 'extra stuff' }

/**
 * Any existing stuff from the `package.json` file is also exposed in the 
 * module as the `package` object.  These vars are also exposed:
 * 1. `filename` path to the `package.json` file
 * 2. `basename` the tip of the package dir
 * 3. `dirname` the parent of the package dir
 */
init(dir, initFile, configData, function (err, data) {
  // the data's already been written to {dir}/package.json
  // now you can do stuff with it
})
```

## More Information

> See [PromZard](https://github.com/npm/promzard) for details about what can go in the config file.

