# config/order-options

- ⚙️ This rule is included in "plugin:config/recommended".
- 🔧 The `--fix` option on the command line can automatically fix some of the problems reported by this rule.

## 📖 Rule Details

enforce ordering of options

- current supports:
  - 'eslint'
  - 'stylelint'
  - 'prettier'

### 👎

```js
/*eslint config/order-options: "error"*/

// .eslintrc.js

module.exports = {
  rules: {...},
  plugins: [...],
}

```

### 👍

```js
/*eslint config/order-options: "error"*/

// .eslintrc.js

module.exports = {
  plugins: [...],
  rules: {...},
}
```

## 🔧 Options

### `override`

```json
{
  "rules": {
    "config/order-options": [
      "error",
      {
        "override": [
          {
            order: ["extends", "rules", "plugins"],
            filenames: [".eslintrc.override.js"]
          }
        ]
      }
    ]
  }
}

{
  "rules": {
    "config/order-options": [
      "error",
      {
        "override": [
          {
            order: "eslint",
            filenames: [".eslintrc.override.js"]
          }
        ]
      }
    ]
  }
}
```

- `override` (`object[]`) ... Override the order-options default setting.
  - `order` (`string[] | 'eslint', 'stylelint', 'prettier'`) ... Specify the ordering of config's options key.
    - Default ... See [](https://github.com/tyankatsu0105/eslint-plugin-config/blob/master/lib/util/configOptionKeys.ts)
  - `filenames` (`string[] | 'eslint', 'stylelint', 'prettier'`) ... Specify the filenames that apply order.
    - Default ... See [](https://github.com/tyankatsu0105/eslint-plugin-config/blob/master/lib/util/configFilenames.ts)
