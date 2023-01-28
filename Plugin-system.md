## Folder structure
Plugin structure can be found on [[Frontend development guidelines]]

## Commands
Execute from `cloudbeaver/webapp`<br>
```yarn run bootstrap```

Load all dependencies and init workspaces<br>
```yarn run build```

Build all packages (plugins and the application) and the result will be placed in the `packages/{package-name}/lib` folder<br>
```yarn run lint```

Lint all code<br>
```yarn run lint-fix```

Lint all code and fix

## Build plugin
To build a single plugin execute
```
yarn lerna run build --stream --scope=@cloudbeaver/plugin-name
```

## Build product
Product folder structure can be found on [[Frontend development guidelines]]<br/>
The only difference in the build command is:<br>
`"build": "core-cli-build --mode=production --config ../core-cli/configs/webpack.product.config.js",`<br>
it uses product config, also contains `dev` command for starting development local build <br>
`"dev": "core-cli-build serve --mode=development --progress --config=../core-cli/configs/webpack.product.dev.config.js --port=3100",`

The application package simple defines the list of plugins that should be included in the build
### Commands
Execute the command to build only the application without rebuilding the plugins<br>
`yarn lerna run build --stream --scope=@cloudbeaver/product-name`

## Development
1. To run a development build that watches file changes and rebuilds, you can use the `dev` command:<br>
`yarn lerna run dev --stream --scope=@cloudbeaver/product-default -- -- --env server=http://backend.server:8095`<br>
It starts the dev server for `product-default`. It also proxies backend requests to `http://backend.server:8095`

2. Navigate `localhost:3100` to open the application

## Static assets
You can keep static assets like images, favicon, etc in the `public` folder in the plugin packages or app package.

Assets such as these will be copied to the application distributive. Assets with the same name will overwrite one another, but the Application public assets have higher priority over them all.

## Localization
See the example in the `core-administration` `AdministrationLocaleService.ts` and `locales` folder