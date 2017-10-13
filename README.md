#### An ESLint [Shareable Config](http://eslint.org/docs/developer-guide/shareable-configs) for [javascript postmodern style](https://github.com/valedaemon/eslint-config-postmodern)

## Install

```bash
npm install eslint-config-postmodern
```

## Usage

Shareable configs are designed to work with the `extends` feature of `.eslintrc` files.
You can learn more about
[Shareable Configs](http://eslint.org/docs/developer-guide/shareable-configs) on the
official ESLint website.

To use the javascript postmodern style shareable config, first run this:

```bash
npm install --save-dev eslint-config-postmodern eslint-plugin-promise eslint-plugin-import eslint-plugin-node
```

Then, add this to your .eslintrc file:

```
{
  "extends": "postmodern"
}
```

You can override settings from the shareable config by adding them directly into your
`.eslintrc` file.
