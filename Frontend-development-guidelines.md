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
Content of this folder will be copyed to `lib` folder.<br/>
Make sure that plugin in the product dependencies list, othervise static content won't be coppied.
