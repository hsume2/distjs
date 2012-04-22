distjs
======

DistJS is an opinionated way to package your code and its dependencies into one distributable file.

## Opinions

1. `make build` generates a single JS file in the `dist` folder (can be customized; see below)
2. Name of dist file should match name of module (snake-cased; see below)
3. Generally unobtrusive. Exposes 1 external variable matching the name of the module (camel-cased)
4. NPM compatible (`package.json`)
5. The dist file encapsulates __all__ of its dependencies
6. Any dependencies must also adhere to these opinions

## Customization

You can customize how a dependency is evaluated by the following customizations to your `package.json`.

### package.json

```json
{
  ...
  "dist": {
    "<module_name>": {
      "make": "<build script command>",
      "fileName": "<filename to use from module>"
    }
  },
  ...
}
```
