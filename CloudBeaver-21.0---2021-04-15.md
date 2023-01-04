### CloudBeaver 21.0 - 2021-04-15

Changes since 1.0.1



* Administration:
    * new tabs have been added for:
        * server management,
        * user management,
        * connection management;
    * notifications have been added about changes in the user management and connection management tabs;
    * the Administration menu is now available when the general authentication is disabled.
* Access Management:
    * user authentication and user roles are now available;
    * an embedded database for user management has been added.
* Connections:
    * SSH support has been added;
    * fields for advanced connection settings are now available in the Connection dialog;
    * connection name can be set in the connection dialog;
    * сonnections can be edited;
    * automatic search of local databases is now available;
    * new drivers have been added:
        * Clickhouse,
        * Oracle, 
        * SQL Server, 
        * Trino (Presto), 
        * Derby Server
        * H2 embedded.
* DB Navigator: 
    * the number of displayed objects have been limited to improve application performance;
    * active connections are now highlighted;
    * changing of a database view, Simple or Advanced, is available;
    * system database objects can be shown or hidden;
    * users can refresh objects in the Navigator tree.
* Data Editor:
    * the Value panel is available for viewing and editing data;
    * display of spatial data is supported in the Value panel;
    * headers of sorted columns are highlighted;
    * filters have been added for table data;
    * users can cancel table data loading;
    * performance has been improved.
* SQL Editor:
    * SQL autocomplete has been improved.
* Metadata Editor:
    * all connections and tabs are now restored after re-login;
    * unsupported objects have been hidden.
* Log viewer:
    * all errors and warnings are displayed for the current session;
    * users can view error details.
* Easy configuration:
    * user authentication and manual connection creation are enabled by default.
* Data export is available for tables.
* New page with the product information is available in the Settings menu.
* Docker environment support has been added.
* Easy access to server logs are now available for administrators (/api/logs/).
* All notifications have a new design.
* A lot of UI fixes and improvements have been made.