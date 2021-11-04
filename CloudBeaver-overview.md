## Features
* [Open connection to remote database](#open-connection-to-remote-database)
* Support for preconfigured connections described in deploy config file
* [Navigate and observe database structure: schemas, tables, views indexes, etc](#navigate-database-structure)
* [View properties of database objects](#view-properties-of-database-object)
* [View and edit table data](#view-and-edit-table-data)
* [Execute SQL queries](#execute-sql-query)

## Overview

### Open connection to remote database
1. Select *Connection > Manual > Custom* in a main menu
2. Select database
3. Set connection options and driver properties and press **Connect** button

![Screenshot 2021-08-12 at 14 02 11](https://user-images.githubusercontent.com/51405061/129186197-b7dd3e15-83d7-4e2c-84a3-241874c7dda5.png)

![Screenshot 2021-08-12 at 14 00 38](https://user-images.githubusercontent.com/51405061/129186034-96040db1-0755-4805-89dd-2db9e42d4ac2.png)

### Navigate database structure
After the connection has been established, the left application panel contains a navigation tree with a database structure
1. Click element in the the tree to open/close nested elements
2. Double-click to open object details on the right application panel
3. Hover element and click on the burger icon to open a context menu of the element
  * the context menu of a connection allows you to close the connection (**Disconnect**) or open the SQL editor (**SQL**)

![Navigation tree](https://github.com/dbeaver/cloudbeaver/wiki/images/navigation-tree.png)

### View properties of database object
1. Open a new connection
2. Select a desired object in the navigation tree, then double-click on it
3. Object property viewer is opened on the right panel

![Property view](https://github.com/dbeaver/cloudbeaver/wiki/images/property-view.png)

### View and edit table data
1. Open a new connection
2. Select a table element in the navigation tree, then double-click on it
3. Table viewer is opened in the right panel

![Table view](https://github.com/dbeaver/cloudbeaver/wiki/images/table-view.png)

**Edit cell**

Double-click cell to edit it. You can submit changes or cancel editing.

**Note** Submitted changes will be immediately applied to the database

![Screenshot 2021-08-12 at 14 05 37](https://user-images.githubusercontent.com/51405061/129186636-508691e7-e7dc-4e63-b35d-67644f36d540.png)

**Copy cells**
* Use drag-n-drop to select a range of cells
* Press Ctrl to add a new selection to the existing one
* Click the index cell to select a row
* Click the column cell to select a column

**Note** If the  data table is big and only part of it is downloaded, only the loaded cells will be selected
* Press **Ctrl-C** to copy the selected cells to the clipboard in CSV format

### Execute SQL query
1. Open a new connection
2. Click **SQL** in the main menu
3. SQL editor with results panel is opened
4. Write SQL query and press **Ctrl-Enter** or click the **Execute** icon
5. Query results will be shown in a tab on the SQL results panel

![SQL Editor](https://github.com/dbeaver/cloudbeaver/wiki/images/sql-editor.png)

