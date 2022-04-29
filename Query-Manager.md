# Query Manager

CloudBeaver EE persists all executed queries in the internal database. Administrators can use the Query Manager to see all users' queries. 

Queries are displayed in the table which contains execution statistics (execution time, duration, number of updated rows, errors, etc). The number of displayed queries cannot exceed 2000 rows. The newest queries are displayed at the top of the list by default.

To open **the Query Manager** go to the Administration and select the Query Manager tab. 

![Query Manager view](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_manager_view.png)

If you want to find a query by text, use the Search field above the table. 

## Query Manager Options

Press the filter button on the right of the Search field to find more Query Manager options.

![query_manager_filter_button](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_manager_filter_button.png)

**1.** Filter conditions can be configured:

* by a query type and an object type;
* by a query status;
* by a date;
* by a user;
* by a driver.

![query_manager_filter_by_users](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_manager_filter_by_users.png)

**2.** Queries can be sorted in a different order:

* by a user;
* by a driver;
* by a query text.

![query_manager_sorting_by_users](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_manager_sorting_by_users.png)

**3.** The number of loaded queries per one time can be changed in the Row Count field. Once you scroll to the last query of the current portion, the next portion (next N queries) is loaded. Setting the maximum number of rows (2000 queries) can slow down the application.

**4.** The auto-refresh mode can be used to update the query history automatically.

![query_manager_filter_by_users](https://github.com/dbeaver/cloudbeaver/wiki/images/query_manager/query_manager_auto_refresh.png)

To turn on the auto-refresh enable it in the Query Manager Options or press the auto-refresh button on the right of the Search field. The additional settings allow you to:
* set a custom auto-refresh interval;
* stop the auto-refresh mode if new queries aren’t received due to an error.

**5.** To return to the default settings, press the Restore Defaults button at the bottom part of the Query Manager Options.
