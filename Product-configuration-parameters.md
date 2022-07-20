### Product config structure
example of packages:<br/>
`core-ui` (package name) -> `ui` (name in config)<br/>
`plugin-notifications` (package name) -> `notifications` (name in config)
```
{
  core: {
    [core package name]: {
      [property name]: [property value]
    },
    ...
  },
  plugin: {
    [plugin package name]: {
      [property name]: [property value]
    },
    ...
  }
}
```

### Product config example
```javascript
{
    // Global properties
    core: {
        administration: {
            baseFeatures: [],
        },
        authentication: {
            baseAuthProvider: 'local',
            primaryAuthProvider: 'local'
        },
        browser: {
            'cookies.disabled': false,
        },
        theming: {
            defaultTheme: "light"
        },
        localization: {
            defaultLanguage: "en"
        },
        'navigation-tree': {
            childrenLimit: 500,
            editing: true,
            deleting: true,
        }
    },
    plugin: {
        'sql-editor': {
            maxFileSize: 100
        },
        notifications: {
            notificationsPool: 5,
            maxPersistentAllow: 5,
        },
        'data-spreadsheet': {
            hidden: false
        },
        'data-viewer': {
            disableEdit: false
        },
        'log-viewer': {
            refreshTimeout: 3000,
            maxLogRecords: 1000,
            logBatchSize: 2000,
            maxFailedRequests: 3,
        },
        'resource-manager': {
            disable: false
        },
        'data-export': {
            disabled: false
        },
        'erd-viewer': {
            maxColumnsToDisplay: 15000
        }
    }
}
```

### Shortcuts
Config below is equivalent to example config for plugins: 'log-viewer', 'resource-manager', 'data-export', 'erd-viewer'
```javascript
{
  ...
  'plugin.log-viewer.refreshTimeout': 3000,
  'plugin.log-viewer.maxLogRecords': 1000,
  'plugin.log-viewer.logBatchSize': 2000,
  'plugin.log-viewer.maxFailedRequests': 3,
  'plugin.resource-manager.disabled': fasle,
  'plugin.data-export.disabled': fasle,
  'plugin.erd-viewer.maxColumnsToDisplay': fasle,
}
```


### Configuration file locations
`webapp/packages/product-default/src/config.json5` (webapp)<br/>
`conf/product.conf` (server)<br/>
`workspace/.data/.product.runtime.conf` (runtime)<br/>
listed in priority order<br/>

### Table of settings

| Variable                                | Value | Description                                      |
|-----------------------------------------|-------|--------------------------------------------------|
| core.user.defaultTheme                  | light | Default theme (light or dark)                    |
| core.user.defaultLanguage               | en    | Default language (language code)                 |
| core.app.logViewer.refreshTimeout       | 3000  | Log viewer refresh interval in ms                |
| core.app.logViewer.maxLogRecords        | 2000  | Maximum rows in log viewer                       |
| core.app.logViewer.maxFailedRequests    | 3     | Count failed log viewer request before disabling |
| core.app.navigationTree.childrenLimit   | 500   | Maximum children in navigation tree              |
| core_events.notificationsPool           | 5     | Maximum notifications                            |
| plugin_data_export.disabled             | true  | Disable data export functionality                |
| plugin_resource_manager.disabled        | false | Disable Resource Manager functionality           |
| core.app.sqlEditor.maxFileSize          | 100   | Max size of sql script that can be uploaded (KB) |
| core.app.metadata.deleting              | true  | Allow deleting metadata objects                  |
| core.app.metadata.editing               | true  | Allow editing metadata objects                   |
| core.app.dataViewer.disableEdit         | false | Disable data editing inside the Data Viewer      |
| core.authentication.primaryAuthProvider | local | Primary auth provider                            |
| core.cookies.disabled                   | false | Whether an app can use cookies or not            |

### Explanation
For example, if you want to disable the data export functionality and increase refresh timeout for the [[Log Viewer|Log-viewer]], you can do it this way.
1. Open or create `.product.runtime.conf`
2. Paste the following code
```javascript
{
  plugin: {
    "log-viewer": {
      refreshTimeout: 7000
    },
    'data-export': {
      disabled: false
    },
  }
}
```


