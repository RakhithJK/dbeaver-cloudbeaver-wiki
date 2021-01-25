## Folder structure
```
|-cloudbeaver
  |-webapp                 # all frontend code is here
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
execute from `cloudbeaver/webapp`

```yarn run bootstrap```

load all dependencies and init workspaces

```yarn run build```

build all packages (plugins and the application) the result will be placed in `packages/{package-name}/lib` folder

```yarn run lint```

lint all code

```yarn run lint-fix```

lint all code and fix

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
only difference in build command: `"build": "core-cli-build --mode=production --config ../core-cli/configs/webpack.product.config.js",` it uses product config, also contains `dev` command for starting development local build `"dev": "core-cli-build serve --mode=development --progress --config=../core-cli/configs/webpack.product.dev.config.js --port=3100",`

The application package simple defines the list of plugins that should be included in the build
### Commands
Execute command to build only application without rebuilding plugins
`lerna run build --stream --scope=@cloudbeaver/product-name`

## Development
1. To run a development build that watches file changed and rebuilds you can use the `dev` command:
`lerna run dev --stream --scope=@cloudbeaver/product-default -- -- --env server=http://backend.server:8095`
it starts dev server for `product-default` and proxies backend requests to `http://backend.server:8095`

2. Navigate `localhost:3100` to open the application

## Static assets
You can keep static assets like images, favicon, etc in `public` folder in plugin packages or app package

All such assets will be copied to application distributive. Assets with the same name will overwrite one another but it is known that Application public assets win.

## Localization
See the example in the `core-administration` `AdministrationLocaleService.ts` and `locales` folder