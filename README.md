# mj-pa
## A custom [Prettier](https://prettier.io) config tailored for JavaScript environments

#### mj-pa == make-javascript-pretty-again!
#### Because what javascript developer doesn't love a good one-liner? :)

## Usage
IMPORTANT: You must have [Prettier](https://www.npmjs.com/package/prettier) installed in your project for [mj-pa](https://www.npmjs.com/package/mj-pa) to work.

#### [View it on npm](npmjs.com/package/mj-pa)
#### [Test it on RunKit](https://runkit.com/killshot13/mj-pa-runkit)

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
