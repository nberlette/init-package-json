# 📦  `init-package-json`

A node module to get your node module started.

[![Build Status](https://secure.travis-ci.org/npm/init-package-json.svg)](http://travis-ci.org/npm/init-package-json)

## Usage: *Command Line Interface*

#### 1. First, install *globally* to expose the binary

```bash
yarn global add init-package-json

# or with npm
npm i --global init-package-json
```

#### 2. Run the `npm-init` command

```bash
npm-init
```

#### Alias to `yarn-init` 

If you use [yarn](https://yarnpkg.com) and don't like the idea of running `npm-init`, you're not alone. I found the most painless and quickest fix to be a simple addition to my `.bash_aliases` file:

```bash
echo "alias yarn-init='npm-init'" >> ~/.bash_aliases && source ~/.bash_aliases
```

> You can also use this alias to add flags or arguments to the command, giving you a nice shorthand option.

---



### Usage: *JavaScript or TypeScript install helper script*

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

