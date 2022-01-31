The Database Navigator is the main tool to work with the structure and content of databases. It is located on the left-hand side of the page.

[[https://github.com/dbeaver/cloudbeaver/wiki/images/administration/server_configuration/navigator_view.png]]

The Database Navigator contains a tree of objects. Each object in the tree has its own context menu. The tree can contain the following objects:

-   Folders 

-   Database connections

-   Database objects - various depending on the database type, such as Tables, Views, Columns, Indexes, etc.

To open the context menu for an object, hover your cursor over the object in the Database Navigator and click the sandwich button to the right of the object.

The following table summarizes the context menu items for all types of objects that may appear in the tree. Note that the presence or absence of the context menu items for an object depends on the database and object types.

| Menu item       | Description                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Open            | Opens an object in a separate Document viewer                                                                                                                                                                              |
| SQL Editor      | Opens a new SQL Editor for the connection                                                                                                                                                                                  |
| Connection view | Changes the view of the Database Navigator                                                                                                                                                                                   |
| Edit Connection | Opens the Connection Configuration window that allows the configuration of connection settings                                                                                                                                      |
| Disconnect      | Disconnects from the database                                                                                                                                                                                              |
| Delete          | Deletes an object.<br/> **WARNING!** The Delete menu item removes the object not only from the tree but from the database itself or the file system, and this action is irreversible.                              |
| Refresh         | Refreshes the object’s subnodes – mostly used for refreshing schemas                                                                                                                                                           |
| Rename          | Opens the Rename dialog box for an object                                                                                                                                                                                  |
| Generate SQL    | Opens a submenu on which you can select the type of SQL query to generate:<br/>- SELECT<br/>- INSERT<br/>- UPDATE<br/>- DELETE<br/>- MERGE<br/>- DDL<br/> Clicking one of the items (for example INSERT) generates a relevant query in a separate window |
| Export          | Opens the Export window for table data export                                                                                                                                                                              |

**To establish a database connection**, do one of the following:

- open the connection;

- expand the connection in the Database Navigator;

- open the SQL Editor for the connection.