# mj-pa

[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier) | [![Known Vulnerabilities](https://snyk.io/test/github/killshot13/mj-pa/badge.svg)](https://snyk.io/test/github/killshot13/mj-pa)

 > 👉 FUN FACT: `mj-pa` is short for `make-javascript-pretty-again`— because what javascript developer doesn't love a good one-liner? 😎

---

## about

 `mj-pa` is a custom [Prettier](https://prettier.io) config tailored to format JS, JSON, & JSX code. Best results will be realized when `mj-pa` is used to extend Prettier in a React- or Vue-based environment.

 [View on RunKit](https://runkit.com/killshot13/mj-pa-runkit/3.0.0)

Naturally opinionated, `mj-pa` was derived from and directly extends the almost equally opinionated Prettier formatting tool.

![output of `.prettierrc.json`](https://github.com/killshot13/mj-pa/raw/main/resources/config.svg)
*output of `.prettierrc.json`*

---

## usage

> IMPORTANT: You must have [Prettier](https://www.npmjs.com/package/prettier) installed in your project for [mj-pa](https://www.npmjs.com/package/mj-pa) to work properly.

### installation

Using npm

```shell
npm install --save-dev mj-pa
```

Using yarn

```shell
yarn add -D mj-pa
```

### configure

Edit the `package.json` file for your project to extend Prettier with `mj-pa`. Or, to be more specific, copy the following line of code and paste it underneath the `version` line of your project's `package.json` file in the root directory.

```json
{
 "prettier": "mj-pa"
}
```

### run

nothing changes here, run the `check` or `write` command as you normally would

```shell
npx prettier --check .
```

```shell
npx prettier --write .
```

### output

Here is an example of how your VSCode logs will appear when `mj-pa` is used to extend the default configuration so formatting can be applied in turn by the [VS Code plugin](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) for Prettier.

![Sample VSCode log output...mj-pa is extending the default configuration and formatting is being applied by the VS Code plugin for Prettier.](https://github.com/killshot13/mj-pa/blob/main/resources/mjpa-vscode-output.svg)

---

If you have any questions, comments, or suggestions, you can open a pull request or [drop me an email](mailto:dmreh@outlook.com)

To learn more about how Prettier works, or to create your own configuration file, you can reference the [Prettier documentation](https://prettier.io/docs/en/index.html)
