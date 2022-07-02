# mj-pa

## v2.0.0

[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier) | [![Known Vulnerabilities](https://snyk.io/test/github/killshot13/mj-pa/badge.svg)](https://snyk.io/test/github/killshot13/mj-pa) | [![Featured on Openbase](https://badges.openbase.com/js/featured/mj-pa.svg?style=openbase&token=8KO/as8Uw+yL8WMwdVQgOx3aguSx5wE9/WtSp6CYg9Q=)](https://openbase.com/js/mj-pa?utm_source=embedded&amp;utm_medium=badge&amp;utm_campaign=rate-badge)

### `make-javascript-pretty-again` is a custom [Prettier](https://prettier.io) config tailored to format JS, JSON, & JSX code. Best results will be realized when `mj-pa` is used to extend Prettier in a React- or Vue-based environment

### `mj-pa` is naturally opinionated, since it was derived from and directly extends the almost equally opioniated Pretter formatting tool

---

> 👉 **`mj-pa`** — because what javascript developer doesn't love a good one-liner? 😎

---

#### output of the `.prettierrc.json` config file

- [view on runkit](https://runkit.com/killshot13/mj-pa-runkit/2.0.0)

---

![output of the `.prettierrc.json` config file](https://github.com/killshot13/mj-pa/raw/main/resources/config.svg)

---

### v2.0.0 release notes

> **Summary**
>
> - reduced the value of `printWidth` from `90` to `85`
>
> - increased the value of `tabWidth` from `1` to `2`
>
> - adjusted the value of `trailingComma` from `es5` to `all`
> **(NOTE: THE ABOVE IS A BREAKING CHANGE THAT MAY REQUIRE ADDITIONAL CONFIGURATION NOT PREVIOUSLY NEEDED!)**
>
> - replaced the now deprecated `jsxBracketSpacing` option with the new `bracketSpacing`
>
> - adjusted the value of `arrowParens` from `avoid` to `always`
>
> - improved overall aesthetics and functionality of the `mj-pa` formatting config

1.) The new print width addresses an issue on small & mid-size devices where a 90 char line would extend beyond the visible right margin of the editor, particularly VS Code, if the IDE settings are such that both the Activity Bar and File Minimap are rendered on the right-hand side of the editor.

2.) The tab indent modification is an opinionated decision that should improve overall readability and adhere more closely to the [accepted standards](https://google.github.io/styleguide/jsguide.html#formatting-indent). While `mj-pa` does prefer tabs over spaces, to the naked eye at least, this change achieves a nearly identical view when compared to a four-space indent.

3.) The trailing comma rule update was admittedly overdue. To continue using `es5` conventions would have been laughable, and although my styling is arguably rather opinionated, even I am not bold enough to suggest dropping the trailing comma. Since only one option remained, the change was implemented by default. However, this is a breaking change, and therefore a major version update (v2.0.0) was introduced.

**IMPORTANT!**

> Please note that in order to run, JavaScript code is formatted this way [needs an engine that supports ES2017](https://prettier.io/docs/en/options.html#trailing-commas) (Node.js 8+ or a modern browser) or downlevel compilation. This also enables trailing commas in type parameters in TypeScript (supported since TypeScript 2.7 was released in January 2018).

4.) Since this release is already going to throw rocks at glass houses with the trailing comma rule change, there was no reason to continue supporting the `jsxBracketSameLine` object, which was deprecated in Prettier v2.4.0 in favor of the broader `bracketSameLine`. The formatted output is nearly identical anyway.

5.) Since becoming more familiar with arrow functions and type annotations, I can no longer justify my previous support for avoiding parentheses to minimize noise. In the documentation, the authors of Prettier note that a [consistent use of parentheses provides a better experience](https://prettier.io/docs/en/options.html#arrow-function-parentheses) when editing real codebases, and I agree.

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
yarn add -D mj-pa
```

#### configuration

edit the `package.json` file for your project to extend Prettier with `mj-pa`

or, to be more specific, copy the following line of code and paste it underneath the `version` line of your project's `package.json` file in the root directory

```json
{
  "prettier": "mj-pa"
}
```

#### sample CLI output

(sample VSCode log output...mj-pa is extending the default configuration and formatting is being applied by the [VS Code plugin](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) for Prettier)

---
  
![sample VSCode log output...mj-pa is extending the default configuration and formatting is being applied by the VS Code plugin for Prettier.](https://github.com/killshot13/mj-pa/blob/main/resources/mjpa-vscode-output.svg)

---

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
