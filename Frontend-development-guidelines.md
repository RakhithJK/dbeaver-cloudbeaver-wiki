### Structure
```
|-webapp
  |-node_modules                  # dependencies
  |-packages                      # packages folder (contains core-* and plugin-*)
    |-(plugin|core)-name          # plugin name (without @cloudbeaver/)
      |-node_modules              # dependencies
      |-lib                       # after the build will contain the artifact
      |-public                    # put static assets to this folder
      |-src                       # keep source files here
        |-locales                 # contains localization files
          |-en.ts                 # contains array of token localizations
        |-index.ts                # contains re-exports
        |-manifest.ts             # contains list of services, plugin name and description
        |-PluginBootstrap.ts      # common plugin registration and initialization logic
        |-LocaleBootstrap.ts      # plugin localization 
      |-package.json
      |-tsconfig.json
    |-plugin-name-administration  # administration plugin name (without @cloudbeaver/), structure are the same as for core/plugin packages
    |-product-name                # product name (without @cloudbeaver/)
      |-node_modules
      |-lib
      |-public
      |-src
        |-config.json5            # product default configuration
        |-index.html.ejs          # html page template
        |-index.ts                # plugins import & application bootstrap
        |-manifest.ts             # contains list of services, product name and description
        |-ProductBootstrap.ts     # common product registration and initialization logic
      |-package.json
      |-tsconfig.json
```

### Dependencies flow
`core-* <- plugin-* <- plugin-*-administration`<br/>
Core packages can depends only on another core packages.<br/>
Plugins can depends only on another plugins or core packages.<br/>
Administration plugins can depends on any package.<br/>

Please avoid circular dependencies.<br/>

### Static content
Every package can have `public` folder at root folder.<br/>
Content of this folder will be copied to `lib` folder.<br/>
Make sure that plugin in the product dependencies list, otherwise static content won't be copied.

### Debugging
As our web application contains numerous packages, it's crucial to debug the code effectively. One way to achieve this is by utilizing the dev tools panel options tab. For instance, if you intend to debug the executor's handlers, you can navigate to the options tab, press ```ctrl + p```, and search for the service that you wish to debug. Afterward, select the line of code that interests you. On your right-hand side, you'll see a call stack that allows you to identify the cause of the handler execution. This method is also beneficial when you need to debug the function's scope.

<img width="878" alt="image" src="https://user-images.githubusercontent.com/48489896/222736503-2f2bdc92-e8f7-4a89-837d-6bb19cf4e230.png">

### Internal packages validation
Each package comes with a package.json file that lists its internal dependencies. These dependencies are those utilized within the package. Therefore, whenever you import a package into the code, you should add it to the package.json file. You can accomplish this manually or by running the validation task ```lerna run validate-dependencies```. If you're importing only types from a package, you can move this package dependency to devDependencies instead of dependencies. Additionally, you should exclude packages that are imported in the .test files.

