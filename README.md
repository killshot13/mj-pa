# mj-pa v1.2.0 
[![Build Status](https://travis-ci.com/killshot13/mj-pa.svg?branch=main)](https://travis-ci.com/killshot13/mj-pa)
[![Rate on Openbase](https://badges.openbase.com/js/rating/mj-pa.svg)](https://openbase.com/js/mj-pa?utm_source=embedded&utm_medium=badge&utm_campaign=rate-badge)

## A custom [Prettier](https://prettier.io) config tailored for JSX & JS environments

### Why mj-pa? 
### (make-javascript-pretty-again)

#### Because what javascript developer doesn't love a good one-liner? :)

### Configuration Output

> ```
> const mjPa = require("mj-pa")
> 
> Object
> printWidth: 90
> tabWidth: 1
> useTabs: true
> semi: false
> singleQuote: true
> quoteProps: "consistent"
> jsxSingleQuote: true
> trailingComma: "es5"
> bracketSpacing: true
> jsxBracketSameLine: true
> arrowParens: "avoid"
> parser: "typescript"
> proseWrap: "preserve"
> htmlWhitespaceSensitivity: "css"
> vueIndentScriptAndStyle: true
> endOfLine: "lf"
> embeddedLanguageFormatting: "auto"
> ```

[View on Runkit](https://runkit.com/killshot13/runkit-npm-mj-pa)

## v1.2.0 Release Notes

#### Improvements

1. This version was published both to [npm](https://www.npmjs.com/package/mj-pa) and to [Github](https://github.com/killshot13/mj-pa/packages/)!

2. Added the ("parser": "typescript") parameter, which favors the [typescript parser (via @typescript-eslint/typescript-estree)](https://github.com/typescript-eslint/typescript-eslint) over traditional [babel parser (via @babel/parser)](https://github.com/babel/babel/tree/main/packages/babel-parser). This is somewhat of a personal preference, but also a nod to `eslint`, which holds the top spot in overall popularity over other `javascript` linters.

#### Adjustments

1. The `jsxSingleQuote` parameter was changed from `false` to `true`. This decision was based primarily on user feedback which heavily favored not using quotation marks when defining `jsx` classes. It also looks less bulky, which is consistent with the overall intent of `mj-pa`.

2. Changed the ("endOfLine") parameter from `auto` to `lf`. With the exponential increase in popularity for Linux-based development since Microsoft released `wsl2` (Windows Subsystem for Linux v2), there is no longer much justification left for the `auto` setting; which carries the obvious risk of allowing mixed line endings in any shared git repository.

3. That is all for now :)
<br></br>

## Usage

IMPORTANT: You must have [Prettier](https://www.npmjs.com/package/prettier) installed in your project for [mj-pa](https://www.npmjs.com/package/mj-pa) to work properly.

#### **Installation**:

from the command line:

NPM

```
$ npm install --save-dev mj-pa
```

YARN

```
yarn add --dev mj-pa
```

#### **Configuration**:

manually edit the `package.json` file for your project:

to be more specific, copy the following line of code and paste it underneath the `version` line of your project's `package.json` file in the root directory.

```
{
  "prettier": "mj-pa"
}
```

#### **Usage**:

nothing changes here, run the `check` or `write` command as you normally would.

```
npx prettier --check .
```

```
npx prettier --write .
```

To learn more about how Prettier works, or to create your own configuration file, you can reference the [Prettier documentation](https://prettier.io/docs/en/index.html).

If you have any questions, comments, or suggestions, you can open a pull request or [drop me an email](mailto:dmreh@outlook.com).
