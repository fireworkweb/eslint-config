# @fireworkweb/eslint-config

Eslint rule configs for Javascript and Vue.js projects.

## Installation

```bash
# With yarn
yarn add -D @fireworkweb/eslint-config

# With npm
npm install --dev  @fireworkweb/eslint-config
```

## Usage

Currently there are two configs available: `js` for pure javascript projects, `vue` for Vue.js projects and `react` for React projects. The `vue` and `react` configs already includes the `js` config.

After installing, create a `.eslintrc.js` file and add this to your config (add only one):

```js
module.exports = {
    extends: [
        // for javascript project
        '@fireworkweb/eslint-config/js',
        // for vue project
        '@fireworkweb/eslint-config/vue',
        // for react project
        '@fireworkweb/eslint-config/react',
    ],
};
```

### Custom Rules

You can customize any rules ([js](https://eslint.org/docs/rules/), [vue](https://eslint.vuejs.org/rules/)), [react](https://github.com/yannickcr/eslint-plugin-react#list-of-supported-rules)) as this example:

```js
module.exports = {
    extends: [
        '@fireworkweb/eslint-config/js',
    ],
    rules: {
        'no-console': 'off',
    },
};
```

You can also (and probably will) add any specific global variable:

```js
// for vue project
module.exports = {
    extends: [
        '@fireworkweb/eslint-config/vue',
    ],
    globals: {
        Vue: true, // if you set window.Vue
        _: true, // lodash/underscore
        Nova: true, // Laravel Nova
    },
};
```

## License

[MIT](LICENSE.md).
