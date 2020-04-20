# Frontend technical overview

Cloudbeaver frontend is single page application written in [React](https://reactjs.org).
We use [InversifyJS](https://github.com/inversify/InversifyJS) for dependency injection and [MobX](https://mobx.js.org) as state management library. [GraphQL](https://graphql.org) is in use to communicate with the server.

The application is written as a set of plugins organized in [Lerna](https://github.com/lerna/lerna) monorepo. Plugins can be developed independently and added to the final build through mentioning in the configuration file.

The application uses [Reshadow](https://reshadow.dev) library and CSS modules for style incapsulation and supports light and dark themes.

We use [Ag-Grid](https://www.ag-grid.com) to display big and functionally rich tables and [Codemirror](https://codemirror.net/2/) to edit SQL queries.

## Development
1. Run local server as it described in [Build and deploy](https://github.com/dbeaver/cloudbeaver/wiki/Build-and-deploy) section
2. Execute
```
cd webapp/packages/dbeaver
yarn run dev --server=localhost:8978
```
to run Webpack dev server
3. Open `localhost:3100` in web browser

## Plugins
The application consist of several plugins and submoduled located in `webapp\packages` folder
* **core**
* * **app** - Base application folder
* * **assets** - Styles and translation
* * **blocks** - Low-level common visual components
* * **di** - Dependency injection related classes
* * **dialogs** - Main and context menues, modal windows
* * **eventsLog** - Logging
* * **sdk** - GraphQL related services
* * **theming** - Themisation related services and hooks
* **ag-grid-plugin** - wrapper over Ag-Grid
* **basic-connectio-plugin** - provides handling of preconfigured connections
* **custom-connection-plugin** - provides handling of custom connections
* **data-viewer-plugin** - provides Data Table View
* **object-viewer-plugin** - provides Object Property View
* **sql-editor** - provides SQL-editor tab
* **dbeaver** - configure and build all plugins to the final application

