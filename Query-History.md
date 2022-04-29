# Query History

CloudBeaver EE persists all executed queries in the internal database. A logged user can see all his own queries in the Query History. 

To open the Query History select it in the Tools menu on the main page.

![tools_query_history](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/tools_query_history.png)

Queries are displayed in the table which contains execution statistics (execution time, duration, number of updated rows, errors, etc). The number of displayed queries cannot exceed 2000 rows. The query history is updated automatically every 5 seconds by default.

![query_history_open](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_history_open.png)

If you want to find a query by text, use the Search field above the table. 

## Query History Options

Press the filter button on the right of the Search field to find more Query History options:

**1.** Filter conditions can be configured:

* by a query type and an object type;
* by a query status;
* by a date;
* by a driver. 

![query_history_filter_by_driver](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_history_filter_by_driver.png)

**2.** Queries can be sorted in a different order:

* by a driver;
* by a query text.

![query_history_sort_by_driver](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_history_sort_by_driver.png)

**3.** The number of loaded queries per one time can be changed in the Row Count field. Once you scroll to the last query of the current portion, the next portion (next N queries) is loaded. Setting the maximum number of rows (2000 queries) can slow down the application.

**4.** Auto-refresh of the Query History can be turned off in the Query History Options or by pressing the auto-refresh button on the right of the Search field. The additional settings also allow you to:
* set a custom auto-refresh interval;
* stop the auto-refresh mode if new queries aren’t received due to an error.

![query_manager_filter_by_users](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_manager_auto_refresh.png) 

**5.** To return to the default settings, press the Restore Defaults button at the bottom part of the filter dialog.