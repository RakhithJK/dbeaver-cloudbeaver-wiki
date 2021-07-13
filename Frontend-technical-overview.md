CloudBeaver frontend is a single page application written in [React](https://reactjs.org).
We use [InversifyJS](https://github.com/inversify/InversifyJS) for dependency injection and [MobX](https://mobx.js.org) as a state management library. [GraphQL](https://graphql.org) is used to communicate with the server.

The application is written as a set of plugins organized in [Lerna](https://github.com/lerna/lerna) monorepo. The plugins can be developed independently and added to the final build by mentioning it in the configuration file.

The application uses [Reshadow](https://reshadow.dev) library and CSS modules for style incapsulation and supports light and dark themes.

We use [Ag-Grid](https://www.ag-grid.com) to display big and functionally rich tables and [Codemirror](https://codemirror.net/2/) to edit SQL queries.

## Development
1. Run the local server as described in the [Build and deploy](https://github.com/dbeaver/cloudbeaver/wiki/Build-and-deploy) section
2. Execute
```
cd webapp/
lerna run dev --stream --scope=@cloudbeaver/product-default -- -- --env server=localhost:8978
```
to run Webpack dev server

3. Open `localhost:3100` in web browser

## Plugins
The application consists of several plugins and submoduled located in the `webapp\packages` folder
* **core-administration** - Administration API
* **core-app** - Base application folder
* **core-authentication** - Authentication API
* **core-blocks** - Low-level common visual components
* **core-bootstrap** - Common core package
* **core-cli** - Command line tools for building & dev
* **core-connections** - Connections API
* **core-di** - Dependency injection related classes
* **core-dialogs** - Main and context menues, modal windows
* **core-events** - Logging
* **core-executor** - Task scheduling API
* **core-extensions** - Extensions API
* **core-localization** - Localization API
* **core-notifications** - Popup notification components
* **core-plugin** - Plugin API
* **core-product** - Product API
* **core-root** - Permissions, server and session services
* **core-routing** - Routing API
* **core-sdk** - GraphQL related services
* **core-settings** - Settings API
* **core-theming** - Themisation related services and hooks
* **core-utils** - Utilites
* **core-view** - View API
* **plugin-administration** - Application configuration wizard
* **plugin-authentication** - Authentication and users administration
* **plugin-connection-custom** - Provides the handling of custom connections
* **plugin-connection-template** - Provides the handling of template connections
* **plugin-data-export** - Data export from data view
* **plugin-data-spreadsheet** - Wrapper over Ag-Grid
* **plugin-data-viewer** - Provides Data Table View
* **plugin-ddl-viewer** - Provides DDL for database objects
* **plugin-object-viewer** - Provides Object Property View
* **plugin-sql-editor** - Provides SQL-editor tab
* **product-default** - Configure and build all plugins to the final application
