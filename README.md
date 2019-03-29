# babel-plugin-transform-modules-sapui5

> This plugin transforms ES2015 modules to sapui5/openui5

[![NPM version](https://img.shields.io/npm/v/babel-plugin-transform-modules-sapui5.svg?style=flat)](https://npmjs.org/package/babel-plugin-transform-modules-sapui5)

----
## Install

Using npm:

```sh
npm install --save-dev babel-plugin-transform-modules-sapui5
```

## Where to add babel-plugin-import

- [babelrc](https://babeljs.io/docs/usage/babelrc/)
- [babel-loader](https://github.com/babel/babel-loader)

## Example

```javascript
export { default as Button } from './Button';

      ↓ ↓ ↓ ↓ ↓ ↓
      
sap.ui.define(["./Button"], function (_Button) {
  "use strict";
  var _exports = {};

  Object.defineProperty(_exports, "__esModule", {
    value: true
  });
  Object.defineProperty(_exports, "Button", {
    enumerable: true,
    get: function get() {
      return _Button["default"];
    }
  });
  _Button = _interopRequireDefault(_Button);

  function _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { "default": obj }; }

  return _exports;
});

```
