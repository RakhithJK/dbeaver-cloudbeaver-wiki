## Folder structure
```
|-cloudbeaver
  |-webapp # all frontend code is here
    |-packages      # yarn workspaces with lerna packages
      |-builder     # package with build configs, 
      |               provides a simple cli to build the plugins and the application
      |-cloudbeaver # application package
      |-core        # core package with common modules like GraphQL, 
        |             dependency injection, and common app services
        |-di        # dependency injection module
        |-blocks    # the module with basic components - buttons, tabs, tables, lists
        |-sdk       # GraphQL wrapping services
        |-dialogs   # menus, context menus, modal windows
      |-_plugin-template  # empty plugin, use it if you want to create own plugin
      |-data-viewer-plugin # application plugins
      |-basic-connection-plugin 
      |-etc...
```
### Plugin folder structure
plugin builder expect certain folder structure:
```
plugin_name
 |-dist # after the build will contain the artifact
 |-node_modules # dependencies
 |-src # keep source files here
 |-package.json
 |-tsconfig.json
```


Plugin can consist of several modules (see @dbeaver/core plugin, for example)
In this case the folder structure should be next:
```
plugin_name
 |-dist # it will contain the artifact after building
 |-module1
   |-package.json # see example in @dbeaver/core
 |-node_modules # dependencies
 |-src
   |-module1
     |- ... # module source files
 |-package.json
 |-tsconfig.json
 |-modules.js # list of modules in order of dependency (see example in @dbeaver/core)
```

## Commands
execute from `cloudbeaver/webapp`

* ```yarn run bootstrap```

load all dependencies and init workspaces

* ```yarn run build```

build all packages (plugins and the application) the result will be placed in `packages/{package-name}/dist` folder

* ```yarn run clean-dist```

delete `dist` folder in all packages

* ```yarn serve-plugin```

build all plugins and start to watch it - rebuild after any code changes

* ```yarn builder-help```

list of available builder commands (DEV only)

## Build plugin
To build a single plugin execute
```
cd packages/plugin-name
yarn run build
```

## Build application
### Application folder structure
```
|-packages
  |-cloudbeaver
    |-dist
    |-node_modules
    |-index.html.ejs  # application template
    |-plugins-list.js # list of all plugins that should be included into the build
    |-package.json
```
The application package simple defines the list of plugins that should be included into the build
### Commands
Execute commands in packages/cloudbeaver folder to build only application without rebuilding plugins
* `yarn run build`

Build application only. All plugins should have been built before execution of this command

* `yarn run build --mode=development`

Build application with sourcemaps and without minification

* `yarn run build --pluginsList=../../custom/path/to/plugins-list.js`

Allows to build application wuth custom plugins list. Please, include the full filename into the path. 
`yarn run build` is the same as `yarn run build --pluginsList=./plugins-list.js`

## Development
1. Run `yarn run serve-plugin` in `webapp` folder. It builds all plugins, put them in corresponding `/dist` folder and starts to watch. When the code is changed the corresponding plugin will be rebuilt.
2. execute `cd packages\cloudbeaver && yarn run serve-app`. It starts webpack-dev-server and serves application with all packages. The application will be updated after any plugin rebuild.
3. Navigate `localhost:3100` to open the application

* `yarn run serve-app --pluginsList=../../custom/path/to/plugins-list.js` 

serve application with custom plugins list

* `yarn run serve-app --port=4200` 

Define custom webpack dev server port. Default is 3100

* `yarn run serve-app --server=http://localhost:8080`

Define custom location of backend server. Default is http://localhost:8978

**Note** If you are going to modify only certain plugins you don't need to serve all of them. 
* Run 'yarn run serve-plugin' in a plugin folder to serve only this plugin
* In webapp folder you can use Lerna filters to server only set of plugins