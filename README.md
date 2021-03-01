# mj-pa

## make-javascript-pretty-again (v1.3.0)

[![Build Status](https://travis-ci.com/killshot13/mj-pa.svg?branch=main)](https://travis-ci.com/killshot13/mj-pa)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)

[![Rate on Openbase](https://badges.openbase.com/js/rating/mj-pa.svg)](https://openbase.com/js/mj-pa?utm_source=embedded&utm_medium=badge&utm_campaign=rate-badge)

---

### a custom [Prettier](https://prettier.io) config tailored for JSX, React.js, & Node.js environments

#### because what javascript developer doesn't love a good one-liner? :)

### run-kit output

[view on runkit](https://runkit.com/killshot13/runkit-npm-mj-pa)

 ```json
 const mjPa = require("mj-pa")

 Object
  printWidth: 90
  tabWidth: 1
  useTabs: true
  semi: false
  singleQuote: true
  quoteProps: "consistent"
  jsxSingleQuote: true
  trailingComma: "es5"
  bracketSpacing: true
  jsxBracketSameLine: true
  arrowParens: "avoid"
  parser: "typescript"
  proseWrap: "preserve"
  htmlWhitespaceSensitivity: "css"
  vueIndentScriptAndStyle: true
  endOfLine: "lf"
  embeddedLanguageFormatting: "auto"

 ```

---

### v1.3.0 release notes



> **Summary**
>
> * the `index.json` file has become the the `.prettierrc.json` file
>
> * the "mj-pa" config can now be called from the command line
>
> * better overall integration and flexibility has been achieved

1.) Prettier uses cosmiconfig for configuration file support. This means you can configure Prettier via (in order of precedence), with the `.prettierrc.json` conveniently in the middle of the [five available options](https://prettier.io/docs/en/configuration.html)

2.) when using Prettier on the command line, you can now point to mj-pa as your configuration of choice

```shell
Config options:

  --config <path>          Path to a Prettier configuration file
  (.prettierrc, package.json, prettier.config.js).
```

That is all for now :)

---

### usage

> IMPORTANT: you must have [Prettier](https://www.npmjs.com/package/prettier) installed in your project for [mj-pa](https://www.npmjs.com/package/mj-pa) to work properly

#### installation

from the command line

NPM

```shell
npm install --save-dev mj-pa
```

YARN

```shell
yarn add --dev mj-pa
```

#### configuration

manually edit the `package.json` file for your project

to be more specific, copy the following line of code and paste it underneath the `version` line of your project's `package.json` file in the root directory

```json
{
  "prettier": "mj-pa"
}
```

--OR--

use the CLI method shared in the release notes above

#### execution

nothing changes here, run the `check` or `write` command as you normally would

```shell
npx prettier --check .
```

```shell
npx prettier --write .
```

to learn more about how Prettier works, or to create your own configuration file, you can reference the [Prettier documentation](https://prettier.io/docs/en/index.html)

if you have any questions, comments, or suggestions, you can open a pull request or [drop me an email](mailto:dmreh@outlook.com)
