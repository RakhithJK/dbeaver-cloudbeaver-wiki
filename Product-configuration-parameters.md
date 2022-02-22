Some variables can be configured via product.conf (server), or via config.json5 (for webapp).

The list of configurable variables are:

| Variable                                | Value | Description                                      |
|-----------------------------------------|-------|--------------------------------------------------|
| core.user.defaultTheme                  | light | Default theme (light or dark)                    |
| core.user.defaultLanguage               | en    | Default language (language code)                 |
| core.app.logViewer.refreshTimeout       | 3000  | Log viewer refresh interval in ms                |
| core.app.logViewer.maxLogRecords        | 2000  | Maximum rows in log viewer                       |
| core.app.logViewer.maxFailedRequests    | 3     | Count failed log viewer request before disabling |
| core.app.navigationTree.childrenLimit   | 500   | Maximum children in navigation tree              |
| core_events.notificationsPool           | 5     | Maximum notifications                            |
| plugin_erd_viewer.maxColumnsToDisplay   | 7500  | Maximum columns in ERD                           |
| plugin_data_export.disabled             | true  | Disable data export functionality                |
| core.app.sqlEditor.maxFileSize          | 100   | Max size of sql script that can be uploaded (KB) |
| core.app.metadata.deleting              | true  | Allow deleting metadata objects                  |
| core.app.metadata.editing               | true  | Allow editing metadata objects                   |
| core.app.dataViewer.disableEdit         | false | Disable data editing inside the Data Viewer      |
| core.authentication.primaryAuthProvider | local | Primary auth provider                            |

You can also specify these parameters in the config file `/workspace/.data/.product.runtime.conf`. These properties have a higher priority than `product.conf`.

For example, if you want to disable the data export functionality and increase refresh timeout for the [[Log Viewer|Log-viewer]], you can do it this way.
1. Open or create .product.runtime.conf in folder .data
2. Paste the following code
```javascript
{
 "core": {
   "app": {
     "logViewer": {
       "refreshTimeout": 7000
     }
   }
 },
 "plugin_data_export": {
   "disabled": true
 }
}


