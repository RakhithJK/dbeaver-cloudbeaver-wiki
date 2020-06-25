Some variables can be configured via product.conf (server), or in source files in webapp, we planned to add a configuration file for products in the future (for webapp).

List of configurable variables:
| Variable                             | Value | Description                                      |
|--------------------------------------|-------|--------------------------------------------------|
| core.app.logViewer.refreshInterval   | 3000  | Log viewer refresh interval in ms                |
| core.app.logViewer.maxLogEntries     | 1000  | Maximum rows in log viewer                       |
| core.app.logViewer.maxFailedRequests | 3     | Count failed log viewer request before disabling |
| core_events.notificationsPool        | 5     | Maximum notifications                            |