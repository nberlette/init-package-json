<h1 align="center">📦  <code>init-package-json</code></h1>

[![Build Status][build-badge]][build-url] [![yarn add init-package-json][yarn-badge]][yarn-url] [![npm install init-package-json][npm-badge]][npm-url]

--- 

## JavaScript (or TypeScript) setup script  

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
 * Any existing `package.json` file is also exposed in the 
 * module as the `package` object.  These vars are also exposed:
 * 1. `filename` path to the `package.json` file
 * 2. `basename` the tip of the package dir
 * 3. `dirname` the parent of the package dir
 */
init (dir, initFile, configData, (err, data) => {
  // the data's already been written to {dir}/package.json
  // now you can do stuff with it
})
```

> See [PromZard](https://github.com/npm/promzard) for details about what can go in the config.


## Command Line Setup and Usage

#### First, install *globally* to expose the binary

```bash
yarn global add init-package-json

# or with npm
npm i --global init-package-json
```

#### Run `npm-init`, or alias it to `yarn-init` if you're anything like me.

```bash
npm-init
```

I just didn't like the idea of using yarn and running `npm-init`. Voila!:

```bash
echo "alias yarn-init='npm-init'" >> $HOME/.bash_aliases
```

---

  
[build-badge]: https://img.shields.io/travis/com/npm/init-package-json?label=BUILD&logo=travis-ci&logoColor=fff&style=for-the-badge
[build-url]: http://travis-ci.org/npm/init-package-json
[npm-badge]: https://img.shields.io/badge/npm%20install%20-%20init&dash;package&dash;json-red?style=for-the-badge&logo=npm
[npm-url]: https://www.npmjs.com/package/init-package-json
[yarn-badge]: https://img.shields.io/badge/yarn%20add-%20init&dash;package&dash;json-8dddff?style=for-the-badge&logo=yarn&labelColor=444
[yarn-url]: https://www.yarnpkg.com/package/init-package-json
