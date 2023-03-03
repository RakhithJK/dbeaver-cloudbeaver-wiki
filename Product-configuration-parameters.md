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
            baseFeatures: []
        },
        authentication: {
            baseAuthProvider: 'local',
            primaryAuthProvider: 'local'
        },
        browser: {
            'cookies.disabled': false
        },
        theming: {
            defaultTheme: 'light'
        },
        localization: {
            defaultLanguage: 'en'
        },
        'navigation-tree': {
            childrenLimit: 500,
            editing: true,
            deleting: true
        }
    },
    plugin: {
        'sql-editor': {
            maxFileSize: 100
        },
        notifications: {
            notificationsPool: 5,
            maxPersistentAllow: 5
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
            maxFailedRequests: 3
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
Config below is equivalent to example config for plugins: 'log-viewer', 'data-export', 'erd-viewer'
```javascript
{
  ...
  'plugin.log-viewer.refreshTimeout': 3000,
  'plugin.log-viewer.maxLogRecords': 1000,
  'plugin.log-viewer.logBatchSize': 2000,
  'plugin.log-viewer.maxFailedRequests': 3,
  'plugin.data-export.disabled': false,
  'plugin.erd-viewer.maxColumnsToDisplay': false
}
```


### Configuration file locations
`webapp/packages/product-default/src/config.json5` (webapp)<br/>
`conf/product.conf` (server)<br/>
`workspace/.data/.product.runtime.conf` (runtime, highest priority)<br/>
listed in priority order<br/>

### Table of settings

| Variable                                | ~~Deprecated~~                 | Value | Description                                      |
|-----------------------------------------|--------------------------------|-------|--------------------------------------------------|
| plugin.notifications.notificationsPool  | core_events.notificationsPool  | 5     | Maximum notifications                            |
| plugin.notifications.maxPersistentAllow | core_events.maxPersistentAllow | 5     | Maximum presistent notifications                 |
| core.browser.cookies.disabled           | core.cookies.disabled          | false | Whether an app can use cookies or not            |

### Explanation
For example, if you want to disable the data export functionality and increase refresh timeout for the [[Log Viewer|Log-viewer]], you can do it this way.
1. Open or create `.product.runtime.conf`
2. Paste the following code
```javascript
{
  plugin: {
    'log-viewer': {
      refreshTimeout: 7000
    },
    'data-export': {
      disabled: false
    }
  }
}
```


