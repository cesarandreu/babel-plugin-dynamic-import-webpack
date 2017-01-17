# babel-plugin-dynamic-import-node

Babel plugin to transpile `import()` to a promise-wrapped `require()`, for Node.

**NOTE:** Babylon v6.12.0 is required to correct parse dynamic imports.

## Installation

```sh
$ npm install babel-plugin-dynamic-import-node --save-dev
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": ["dynamic-import-node"]
}
```

### Via CLI

```sh
$ babel --plugins dynamic-import-node script.js
```

### Via Node API

```javascript
require("babel-core").transform("code", {
  plugins: ["dynamic-import-node"]
});
```

### Dynamic imports and webpack

Although the specification for `import()` supports a dynamic importing of modules in the browser runtime, webpack's `require.ensure()` is not dynamic and requires a hardcoded string to work correctly. For more information see [webpack's documentation](https://webpack.github.io/docs/context.html#dynamic-requires) on dynamic requires.
