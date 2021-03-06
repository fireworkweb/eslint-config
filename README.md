# @fireworkweb/eslint-config

Eslint rule configs for Javascript and Vue.js projects.

## Installation

To install, add it with `eslint` to your dev dependencies.

```bash
# With yarn
yarn add -D eslint @fireworkweb/eslint-config

# With npm
npm install --dev eslint @fireworkweb/eslint-config
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

Also, you should add this script to your `package.json`:

```json
{
    // ...
    "scripts": {
        // ...
        "lint": "eslint --ext js,vue,jsx ."
    }
}
```

You should customize the extensions (`--ext` parameter) to fit your needs.

Then you can run `yarn lint` or `npm run lint`. To automatically fix some of the errors, you can add `--fix` to the lint command.

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

## Collaborators

| [<img src="https://avatars0.githubusercontent.com/u/11093090?v=3&s=115" width="115"><br><sub>@gabrielboliveira</sub>](https://github.com/gabrielboliveira) | [<img src="https://avatars3.githubusercontent.com/u/17432496?v=3&s=115" width="115"><br><sub>@nkabz</sub>](https://github.com/nkabz) |
|:-:|:-:|
