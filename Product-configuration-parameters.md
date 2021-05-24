Some variables can be configured via product.conf (server), or via config.json5 (for webapp).

List of configurable variables:

| Variable                             | Value | Description                                      |
|--------------------------------------|-------|--------------------------------------------------|
| core.user.defaultTheme               | light | Default theme                                    |
| core.user.defaultLanguage            | en    | Default language                                 |
| core.app.logViewer.refreshTimeout    | 3000  | Log viewer refresh interval in ms                |
| core.app.logViewer.maxLogEntries     | 1000  | Maximum rows in log viewer                       |
| core.app.logViewer.maxFailedRequests | 3     | Count failed log viewer request before disabling |
| core.app.navigationTree.childrenLimit| 500   | Maximum children in navigation tree              |
| core_events.notificationsPool        | 5     | Maximum notifications                            |
| plugin_erd_viewer.maxColumnsToDisplay| 7500  | Maximum columns in ERD                           |
| plugin_data_export.disabled          | false | Disable data export functionality                |

