## Folder structure
```
|-cloudbeaver
  |-webapp # all frontend code is here
    |-packages # yarn workspaces with lerna packages
      |-builder # package with build configs, provide a simple cli to build the plugins and the application
      |-dbeaver # application package
      |-core # core package with common modules like GraphQL, dependency injection, and common app services
        |-di      # dependency injection module
        |-blocks  # the module with basic components - buttons, tabs, tables, lists
        |-sdk     # GraphQL wrapping services
        |-dialogs # menus, context menus, modal windows
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
```yarn run bootstrap```
load all dependencies and init workspaces
```yarn run build```
build all packages (plugins and the application) the result will be placed in `packages/{package-name}/dist` folder
```yarn run clean-dist```
delete `dist` folder in all packages
```yarn serve-plugin``
build all plugins and start to watch it - rebuild after any code changes