# Frontend technical overview

Cloudbeaver frontend is single page application written in [https://reactjs.org](React).
We use [[https://github.com/inversify/InversifyJS|InversifyJS]] for dependency injection and [[https://mobx.js.org|MobX]] as state management library. 

The application is written as a set of plugins organized in [[https://github.com/lerna/lerna|Lerna]] monorepo. Plugins can be developed independently and added to the final build through mentioning in the configuration file.

The application uses [[https://reshadow.dev||Reshadow]] library and CSS modules for style incapsulation and supports light and dark themes.

We use [[https://www.ag-grid.com|Ag-Grid]] to display big and functionally rich tables and [[https://codemirror.net/2/|Codemirror]] to edit SQL queries.

## Development
1. Run local server as it described in [[https://github.com/dbeaver/cloudbeaver/wiki/Build-and-deploy|Build and deploy]] section
2. Execute
```
cd webapp/packages/dbeaver
yarn run dev --server=localhost:8978
```
to run Webpack dev server
3. Open `localhost:3100` in web browser

## Plugins
The application consist of several plugins and submoduled located in `webapp\packages` folder
* **Core**
** **app** - base application folder
