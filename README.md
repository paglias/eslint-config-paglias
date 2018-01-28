# eslint-config-paglias

A set of reusable ESLint rules based on [Airbnb JavaScript Style Guide() {](https://github.com/airbnb/javascript).

Information about installation and usage can be found at http://eslint.org/docs/developer-guide/shareable-configs.

## Available Configs

### eslint-config-paglias
### eslint-config-paglias/lib/vue
### eslint-config-paglias/lib/node

## TODO

### general
- describe rules

### vue

```
  // check if imports actually resolve
  settings: {
    'import/resolver': {
      webpack: {
        config: 'build/webpack.base.conf.js'
      }
    }
  },
  // add your custom rules here
  rules: {
    // don't require .vue extension when importing
    'import/extensions': ['error', 'always', {
      js: 'never',
      vue: 'never'
    }],
    // disallow reassignment of function parameters
    // disallow parameter object manipulation except for specific exclusions
    'no-param-reassign': ['error', {
      props: true,
      ignorePropertyModificationsFor: [
        'state', // for vuex state
        'acc', // for reduce accumulators
        'e' // for e.returnvalue
      ]
    }],
    // allow optionalDependencies
    'import/no-extraneous-dependencies': ['error', {
      optionalDependencies: ['test/unit/index.js']
    }],
    // allow debugger during development
    'no-debugger': process.env.NODE_ENV === 'production' ? 'error' : 'off'
  }
```

?
taken from vuejs-templates/webpack