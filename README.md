# react

A [React Transform](https://github.com/gaearon/babel-plugin-react-transform) that enables hot reloading React classes using JSPM. Hot module replacement is supported via [jspm-hot-reloader](https://github.com/capaj/jspm-hot-reloader) and [systemjs/plugin-babel](https://github.com/systemjs/plugin-babel). This is based on [react-transform-hmr](https://github.com/gaearon/react-transform-hmr) by [Dan Abramov](https://github.com/gaearon).

## Installation

First, install the [Babel plugin](https://github.com/gaearon/babel-plugin-react-transform):

```
jspm install react-transform=npm:babel-plugin-react-transform
```

Then, install the transform:

```
jspm install npm:react-transform-jspm-hmr
```

### Configuration

For now, you have to download [babel-plugin](https://github.com/systemjs/plugin-babel) manually and edit `options.plugins` to `["react-transform"]`.

In your `config.js`:

```js
{
  babelOptions: {
    "optional": [
      "runtime",
      "optimisation.modules.system"
    ],
    "extra": {
      "react-transform": {
        "transforms": [{
          "transform": "react-transform-hmr"
        }]
      }
    }
  }
}
```

Then load the files you wish to transform with the `import jsx from './component!babel'` syntax or use a meta in `config.js`

```js
{
  meta: {
    "some/files/*": {
      "loader": "babel-loader"
    }
  }
}
```

## License

MIT
