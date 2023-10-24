# **Change Log** 📜📝

All notable changes to _mj-pa_ will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [**3.0.0**] - 2023-10-23

### Added (3.0.0)

* Support was added for the new `singleAttributePerLine` option with its value set to `true`.

### Changed (3.0.0)

* Improvements were made to the overall aesthetics and functionality of `mj-pa`.

### Removed (3.0.0)

* All options :arrow_down: which did not alter the config but simply repeated the underlying Prettier default values were removed.

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

* More specifically, this determination was made specifically using the defaults assigned in [Prettier v3.0.0](https://github.com/prettier/prettier/tree/3.0.0). **(NOTE: THIS A BREAKING CHANGE THAT MAY REQUIRE ADDITIONAL CONFIGURATION NOT PREVIOUSLY NEEDED!)**

---

## [**2.0.0**] - 2023-10-23

### Added (2.0.0)

* The `bracketSameLine` option replaces the now deprecated `jsxBracketSameLine`. Since this release is already going to throw rocks at glass houses with the trailing comma rule change, there was no reason to continue supporting the `jsxBracketSameLine` option, which was deprecated in Prettier v2.4.0 in favor of the broader `bracketSameLine.` The formatted output is nearly identical anyway.

### Changed (2.0.0)

* The value of `printWidth` has been reduced from from `90` to `85`. The new print width addresses an issue on small & mid-size devices where a 90-char line would extend beyond the visible right margin of the editor, particularly VS Code, if the IDE settings are such that both the Activity Bar and File Minimap are rendered on the right-hand side of the editor.
* The value of `tabWidth` has been increased from `1` to `2`. The tab indent modification is an opinionated decision that should improve overall readability and adhere more closely to the [accepted standards](https://google.github.io/styleguide/jsguide.html#formatting-indent). While `mj-pa` prefers tabs over spaces, to the naked eye at least, this change achieves a nearly identical view compared to a four-space indent.
* The value of `trailingComma` has been switched from `es5` to `all` This update was admittedly overdue. To continue using `es5` conventions would have been laughable, and although my styling is arguably rather opinionated, even I am not bold enough to suggest dropping the trailing comma. Since only one option remained, the change was implemented by default. However, this a breaking change, and therefore a major version update (v2.0.0) was introduced.

  > **(NOTE: THE ABOVE IS A BREAKING CHANGE THAT MAY REQUIRE ADDITIONAL CONFIGURATION NOT PREVIOUSLY NEEDED!)**
  > Please note that to run, JavaScript code formatted this way [needs an engine that supports ES2017](https://prettier.io/docs/en/options.html#trailing-commas) (Node.js 8+ or a modern browser) or downlevel compilation. This also enables trailing commas in type parameters in TypeScript (supported since TypeScript 2.7 was released in January 2018).

* The value of `arrowParens` has been transitioned from `avoid` to `always`. Since becoming more familiar with arrow functions and type annotations, I can no longer justify my previous support for avoiding parentheses to minimize noise. In the documentation, the authors of Prettier note that a [consistent use of parentheses provides a better experience](https://prettier.io/docs/en/options.html#arrow-function-parentheses) when editing authentic codebases, and I agree.
* Overall aesthetics and functionality of the `mj-pa` formatting config have been improved. That is all for now :)

#### **Full Changelog (2.0.0)**

* <https://github.com/killshot13/mj-pa/compare/v1.3.1...v2.0.0>

---

## [**1.3.1**] - 2023-10-23

### Fixed (1.3.1)

* Minor bug fixes

#### **Full Changelog (1.3.1)**

* <https://github.com/killshot13/mj-pa/compare/v1.3.0...v1.3.1>

---

## [**1.3.0**] - 2023-10-23

### Added (1.3.0)

* New file `codeql-analysis.yml` by @killshot13 in <https://github.com/killshot13/mj-pa/pull/1>

### Changed (1.3.0)

* The `index.json` file has become the `.prettier.json` file.

**NOTE: Prettier uses `cosmiconfig` for configuration file support. This means you can configure Prettier in five different ways, with the `.prettierrc.json` conveniently in the middle of the available options.**

* Update issue templates by @killshot13 in <https://github.com/killshot13/mj-pa/pull/2>

### Improved (1.3.0)

* The `mj-pa` config is now callable from the command line; when using Prettier on the command line, you can now point to `mj-pa` as your configuration of choice

```sh
# Path to a Prettier configuration file
--config ./mj-pa/.prettierrc.json  
```

Additional config alternatives include .prettierrc,package.json, prettier.config.js

* [ImgBot] Optimize images by @imgbot in <https://github.com/killshot13/mj-pa/pull/3>
* Better overall integration and flexibility achieved

---

## [**1.2.0**] - 2021-12-23

### Added (1.2.0)

* [View it on npm](https://www.npmjs.com/package/mj-pa/v/1.2.0)

* [Test it on RunKit](https://runkit.com/killshot13/mj-pa-runkit)

* `mj-pa` now defines a value for `parser` in `.prettierrc.json`. This decision favors the [typescript parser](https://github.com/typescript-eslint/typescript-eslint) over the more traditional [babel parser](https://github.com/babel/babel/tree/main/packages/babel-parser). While somewhat of a personal preference, this is also a nod to `eslint`, which holds the top spot in overall popularity over other `javascript` linters.

   ```json
   {
    "parser": "typescript"
   }
   ```

### Changed (1.2.0)

* The `jsxSingleQuote` parameter was changed from `false` to `true`. This decision was based primarily on user feedback which heavily favored not using quotation marks when defining `jsx` classes. It also looks less bulky, which is consistent with the generally minimalist approach of `mj-pa`.

  ```json
  {
   "jsxSingleQuote": true
  }
  ```

* The `endOfLine` option changed from `auto` to `lf`. With the exponential increase in popularity for Linux-based development since Microsoft released WSL2 (Windows Subsystem for Linux v2), there is no longer much justification left for the `auto` setting; which carries the obvious risk of allowing mixed line endings in any shared git repository.

  ```json
  {
   "endOfLine": "lf"
  }
  ```

### Improved (1.2.0)

* This version was published both to [npm](https://www.npmjs.com/package/mj-pa/v/1.2.0) and the [Github package registry](https://github.com/killshot13/mj-pa/packages/)!

#### **Full Changelog (1.2.0)**

* <https://github.com/killshot13/mj-pa/compare/v1.0.0...v1.2.0>

---

## [**1.0.0**] - 2021-10-21

### Added (1.0.0)

* First published to the Node Package Manager (npm) registry on 21 October 2020

* [View it on npm](https://www.npmjs.com/package/mj-pa/v/1.0.0)

* [Test it on RunKit](https://runkit.com/killshot13/mj-pa-runkit)

#### **Full Changelog (1.0.0)**

* <https://github.com/killshot13/mj-pa/commits/v1.0.0>
