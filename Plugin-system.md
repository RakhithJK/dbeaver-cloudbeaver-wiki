## Folder structure
```
|-cloudbeaver
  |-webapp                 # all frontend codes are here
    |-packages             # yarn workspaces managed by lerna
      |-core               # core package with common modules like GraphQL, 
        |                    dependency injection, and common app services
        |-cli              # core/plugin/product build configs (webpack, babel)
        |-administration   # administration API
        |-di               # dependency injection module
        |-blocks           # the module with basic components - buttons, tabs, tables, lists
        |-sdk              # GraphQL wrapping services
        |-dialogs          # menus, context menus, modal windows
        |-...              # other modules
      |-plugin
        |-authentication
        |-connection-custom
        |-connection-template
        |-data-export
        |-etc...            # other plugins
      |-product-default     # default application product package (with all plugins)
```
### Plugin folder structure
common folder structure:
```
package_name
 |-node_modules    # dependencies
 |-lib             # after the build will contain the artifact
 |-public          # put static assets to this folder
 |-src             # keep source files here
 |-package.json
 |-tsconfig.json
```

## Commands
Execute from `cloudbeaver/webapp`

```yarn run bootstrap```

Load all dependencies and init workspaces

```yarn run build```

Build all packages (plugins and the application) and the result will be placed in the `packages/{package-name}/lib` folder

```yarn run lint```

Lint all code

```yarn run lint-fix```

Lint all code and fix

## Build plugin
To build a single plugin execute
```
lerna run build --stream --scope=@cloudbeaver/plugin-name
```

## Build product
### Product folder structure is the same as for plugin
```
|-packages
  |-cloudbeaver
    |-node_modules     # dependencies
    |-lib              # after the build will contain the artifact
    |-public           # put static assets to this folder
    |-src              # keep source files here
    |-package.json
    |-tsconfig.json
```
The only difference in the build command is: `"build": "core-cli-build --mode=production --config ../core-cli/configs/webpack.product.config.js",` it uses product config, also contains `dev` command for starting development local build `"dev": "core-cli-build serve --mode=development --progress --config=../core-cli/configs/webpack.product.dev.config.js --port=3100",`

The application package simple defines the list of plugins that should be included in the build
### Commands
Execute the command to build only the application without rebuilding the plugins

`lerna run build --stream --scope=@cloudbeaver/product-name`

## Development
1. To run a development build that watches file changes and rebuilds, you can use the `dev` command:
`lerna run dev --stream --scope=@cloudbeaver/product-default -- -- --env server=http://backend.server:8095`
It starts the dev server for `product-default`. It also proxies backend requests to `http://backend.server:8095`

2. Navigate `localhost:3100` to open the application

## Static assets
You can keep static assets like images, favicon, etc in the `public` folder in the plugin packages or app package.

Assets such as these will be copied to the application distributive. Assets with the same name will overwrite one another, but the Application public assets have higher priority over them all.

## Localization
See the example in the `core-administration` `AdministrationLocaleService.ts` and `locales` folder