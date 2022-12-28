### CloudBeaver 20.0.1 - 2020-12-29

**Changes since 1.0.1**



* Administration:
    * new tabs have been added for:
        * server management,
        * user management,
        * connection management;
    * notifications have been added to the user management and connection management tabs;
    * the Administration menu is now available when the general authentication is disabled.
* Access Management:
    * user authentication and user roles are now available;
    * an embedded database for user management has been added.
* Connections:
    * connection name can be set in the Create connection dialog;
    * automatic search of databases is now available;
    * new drivers have been added:
        * Clickhouse,
        * H2 embedded.
* DB Navigator: 
    * the number of displayed objects have been limited to improve application performance;
    * active connections are now highlighted;
    * users can refresh objects in the Navigator tree.
* Data Editor:
    * filters have been added for table data.
* SQL Editor:
    * SQL autocomplete has been improved.
* Metadata Editor:
    * all connections and tabs are now restored after re-login;
    * unsupported objects have been hidden.
* Easy configuration:
    * user authentication and manual connection creation are enabled by default.
* Data export is available for tables.
* Docker environment support has been added.
* Easy access to server logs are now available for administrators (/api/logs/).
* New loading screen has been added.
* All notifications have a new design.
* A lot of UI fixes and improvements have been made.