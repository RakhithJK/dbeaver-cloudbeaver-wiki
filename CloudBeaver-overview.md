## Features
* [Open connection to remote database](#open-connection-to-remote-database)
* Support for preconfigured connections described in deploy config file
* [Navigate and observe database structure: schemas, tables, views indexes, etc](#navigate-database-structure)
* [View properties of database objects](#view-properties-of-database-object)
* [View and edit table data](#view-and-edit-table-data)
* [Execute SQL queries](#Execute-SQL-query)
## Overview

### Open connection to remote database
1. Select *Connection > New connection > custom* in a main menu
2. Select database
3. Set connection options and driver properties and press **Connect** button

![Select database](https://github.com/dbeaver/cloudbeaver/wiki/images/select-database.png)
![Connection options](https://github.com/dbeaver/cloudbeaver/wiki/images/connection-options.png)

### Navigate database structure
After the connection has been established left application panel contains a navigation tree with a database structure
1. Click element in the the tree to open/close nested elements
2. Double-click to open object details on the right application panel
3. Hover element and click on the burger icon to open a context menu of the element
  * context menu of a connection allows to close connection (**Disconnect**) or open SQL editor (**SQL**)

![Navigation tree](https://github.com/dbeaver/cloudbeaver/wiki/images/navigation-tree.png)

### View properties of database object
1. Open a new connection
2. Select a desired object in the navigation tree, double-click it
3. Object property viewer is opened on the right panel

![Property view](https://github.com/dbeaver/cloudbeaver/wiki/images/property-view.png)

### View and edit table data
1. Open a new connection
2. Select a table element in the navigation tree, double-click it
3. Table viewer is opened on the right panel

![Table view](https://github.com/dbeaver/cloudbeaver/wiki/images/table-view.png)

**Edit cell**

Double-click cell to edit it. You can submit changes or cancel editing.

**Note** Submitted changes will be immediately applied to the database

![Edit cell](https://github.com/dbeaver/cloudbeaver/wiki/images/edit-cell.png)

**Copy cells**
* Use drag-n-drop to select range of cells
* Press Ctrl to add a new selection to the existing one
* Click index cell to select a row
* Click column cell to select a column

**Note** If the  data table is big and only part is downloaded only loaded cells will be selected
* Press **Ctrl-C** to copy selected cells to clipboard in CSV format

### Execute SQL query
1. Open a new connection
2. Click **SQL** in the main menu
3. SQL editor with results panel is opened
4. Write SQL query and press **Ctrl-Enter** or click **Execute** icon
5. Query results will be shown in a tab on the SQL results panel

![SQL Editor](https://github.com/dbeaver/cloudbeaver/wiki/images/sql-editor.png)

