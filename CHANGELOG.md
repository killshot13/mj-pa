# Changelog 📜📝

All notable changes to _mj-pa_ will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [**v3.0.0**]

_(2023-10-24)_

[View it](https://www.npmjs.com/package/mj-pa/v/3.0.0) on npm or [test it](https://runkit.com/killshot13/mj-pa-runkit) on RunKit.

### Added

* Support was added for the new `singleAttributePerLine` option with the value set to `true`.

### Improved

* Improvements were made to the overall aesthetics and functionality.

### Removed

* All options that simply repeated the Prettier default values based on [Prettier v3.0.0] were removed. See the complete list below. :arrow_down:
  
  > **ATTENTION: THIS IS A BREAKING CHANGE; UPDATE WITH CAUTION!**

```json
   {
      "tabWidth": 2,
      "trailingComma": "all",
      "bracketSpacing": true,
      "arrowParens": "always",
      "proseWrap": "preserve",
      "htmlWhitespaceSensitivity": "css",
      "endOfLine": "lf",
      "embeddedLanguageFormatting": "auto"
   }
```
    
#### Full Changelog

* https://github.com/killshot13/mj-pa/compare/v2.0.0...v3.0.0
___

## [**v2.0.0**]

_(2021-09-25)_

[View it](https://www.npmjs.com/package/mj-pa/v/2.0.0) on npm or [test it](https://runkit.com/killshot13/mj-pa-runkit) on RunKit.

### Added

* The `bracketSameLine` option replaces the now deprecated `jsxBracketSameLine`. Since this release is already going to throw rocks at glass houses with the trailing comma rule change, there was no reason to continue supporting the `jsxBracketSameLine` option, which was deprecated in Prettier v2.4.0 in favor of the broader `bracketSameLine.` The formatted output is nearly identical anyway.

### Changed

* The value of `printWidth` has been reduced from from `90` to `85`. The new print width addresses an issue on small & mid-size devices where a 90-char line would extend beyond the visible right margin of the editor, particularly VS Code if the IDE settings are such that both the Activity Bar and File Minimap are rendered on the right-hand side of the editor.
* The value of `tabWidth` has been increased from `1` to `2`. The tab indent modification is an opinionated decision that should improve overall readability and adhere more closely to the [accepted standards](https://google.github.io/styleguide/jsguide.html#formatting-indent). While `mj-pa` prefers tabs over spaces, to the naked eye at least, this change achieves a nearly identical view compared to a four-space indent.
* The value of `trailingComma` has been switched from `es5` to `all` This update was admittedly overdue. To continue using `es5` conventions would have been laughable, and although my styling is arguably rather opinionated, even I am not bold enough to suggest dropping the trailing comma. Since only one option remained, the change was implemented by default. However, this a breaking change, and therefore a major version update (v2.0.0) was introduced.

  > ATTENTION: THIS IS A BREAKING CHANGE; UPDATE WITH CAUTION!
  > 
  > NOTE: To run, JavaScript code formatted this way [needs an engine that supports ES2017](https://prettier.io/docs/en/options.html#trailing-commas) (Node.js 8+ or a modern browser) or downlevel compilation. This also enables trailing commas in type parameters in TypeScript (supported since TypeScript 2.7 was released in January 2018).

* The value of `arrowParens` has been transitioned from `avoid` to `always`. Since becoming more familiar with arrow functions and type annotations, I can no longer justify my previous support for avoiding parentheses to minimize noise. In the documentation, the authors of Prettier note that a [consistent use of parentheses provides a better experience](https://prettier.io/docs/en/options.html#arrow-function-parentheses) when editing authentic codebases, and I agree.

### Improved 

* Overall aesthetics and functionality of the `mj-pa` formatting config have been improved.
  
#### Full Changelog

* https://github.com/killshot13/mj-pa/compare/v1.3.0...v2.0.0
___

## [**v1.3.0**]

_(2021-05-09)_

[View it](https://www.npmjs.com/package/mj-pa/v/1.3.0) on npm or [test it](https://runkit.com/killshot13/mj-pa-runkit) on RunKit.

### Added

* New file `codeql-analysis.yml` by @killshot13 in <https://github.com/killshot13/mj-pa/pull/1>

### Changed

* The `index.json` file has become the `.prettier.json` file.

**NOTE: Prettier uses `cosmiconfig` for configuration file support. This means you can configure Prettier in five different ways, with the `.prettierrc.json` conveniently in the middle of the available options.**

* Update issue templates by @killshot13 in <https://github.com/killshot13/mj-pa/pull/2>

### Improved

* The `mj-pa` config is now callable from the command line; when using Prettier on the command line, you can now point to `mj-pa` as your configuration of choice

_Additional config alternatives include .prettierrc, package.json, and prettier.config.js_

```sh
# Path to a Prettier configuration file
--config ./mj-pa/.prettierrc.json  
```

* [ImgBot] Optimize images by @imgbot in <https://github.com/killshot13/mj-pa/pull/3>
* Better overall integration and flexibility achieved

#### Full Changelog

* https://github.com/killshot13/mj-pa/compare/v1.2.0...v1.3.0
___

## [**v1.2.0**]

_(2020-12-23)_

[View it](https://www.npmjs.com/package/mj-pa/v/1.2.0) on npm or [test it](https://runkit.com/killshot13/mj-pa-runkit) on RunKit.

### Added

* `mj-pa` now defines a value for `parser` in `.prettierrc.json`. This decision favors the [typescript parser](https://github.com/typescript-eslint/typescript-eslint) over the more traditional [babel parser](https://github.com/babel/babel/tree/main/packages/babel-parser). While somewhat of a personal preference, this is also a nod to `eslint`, which holds the top spot in overall popularity over other `javascript` linters.

   ```json
   {
    "parser": "typescript"
   }
   ```

### Changed

* The `jsxSingleQuote` parameter was changed from `false` to `true`. This decision was based primarily on user feedback, which heavily favored not using quotation marks when defining `jsx` classes. It also looks less bulky, which is consistent with the generally minimalist approach of `mj-pa`.

  ```json
  {
   "jsxSingleQuote": true
  }
  ```

* The `endOfLine` option changed from `auto` to `lf`. With the exponential increase in popularity for Linux-based development since Microsoft released WSL2 (Windows Subsystem for Linux v2), there is no longer much justification left for the `auto` setting, which carries the obvious risk of allowing mixed line endings in any shared git repository.

  ```json
  {
   "endOfLine": "lf"
  }
  ```

### Improved

* This version was published both to [npm](https://www.npmjs.com/package/mj-pa/v/1.2.0) and the [Github package registry](https://github.com/killshot13/mj-pa/packages/)!

#### Full Changelog

* https://github.com/killshot13/mj-pa/compare/v1.0.0...v1.2.0
___

## [**v1.0.0**]

_(2020-10-21)_

[View it](https://www.npmjs.com/package/mj-pa/v/1.2.0) on npm or [test it](https://runkit.com/killshot13/mj-pa-runkit) on RunKit.

### Added

* Initial publication to the Node Package Manager (npm) registry.

#### Full Changelog

* https://github.com/killshot13/mj-pa/commits/v1.0.0
___
