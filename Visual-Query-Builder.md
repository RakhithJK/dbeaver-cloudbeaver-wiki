Note: This feature is available in Enterprise and Enterprise for AWS editions only.

# Overview

The Visual Query Builder is a user-friendly visualization tool that can help you to create queries to the database and see results. You do not need to know SQL language to work in it.
The Visual Query Builder may be useful for:
* building queries;
* complex queries analysis;
* easy query editing.

![VQB Cut](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_cut.png)

To open the Visual Query Builder, click the Query Builder tab in the SQL Editor right toolbar.

## Creating a Visual Query

1. Select tables in the Navigator tree and drag-and-drop them into the Visual Query Builder area. The existing connections between the tables will automatically be displayed. The tables will also be added to the SQL expression which can be found in the field to the right of the diagram.

 ![vqb dnd](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/dnd.png)

2. To create a new join between tables, connect their columns holding the left mouse button. The connection between the selected columns of the tables will appear in the diagram and the Inner Join will be added to the SQL script. 

 ![vqb create_join](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/create_join.png)

3. You can change a join type clicking the join label on the connection line.
4. To remove a join between tables, click on the line, then press the Delete button. The connection will be removed from the diagram and the join will disappear from the SQL script.
5. By default all tables’ columns are included in the query. If you only want to see certain columns in your query result, select the checkbox near the column name.

 ![vqb column checkbox](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_checkbox.png)

### Filtering

6. WHERE condition with the filter value is used for filtering. To add a filter, write it in the top filter field.

| Column name                                                                                                   | Operation Sign                                                  | Value                                                                                                                            |
|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| A table column name. You have to write a table alias before if another column has the same name | The most common signs:  =,  >,  <,  <>,  LIKE,  ILIKE,  BETWEEN | A column value, used as a parameter. Text and time values must be rounded by single quotes, numeric values do not need any quotes |

Filter example:

 ![vqb_filter](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_filter.png)

### Sorting

7. To apply a sorting condition to a column, press the sorting icon next to a column name on the diagram. The column will be sorted in ascending order and the conditional expression ORDER BY will be added to the SQL script. 
To sort the column in descending order,  press the sorting icon again to select the down arrow. 
If you want to remove a condition, continue to click the sorting icon to deactivate it. 
Sorting can be applied to multiple columns in different tables. First, apply sorting on the first column you wish to sort, and then on the second, third and so on.
You can sort numbers, texts, dates, time and other values.

 ![vqb sorting](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_sorting.png)

## Executing a Visual Query
Use the Execute SQL statement button  ![vqb Execute SQL statement button](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/execute_statement.png) on the left pane to execute a query and get the results in the same tab. If you want to see the result in a new tab, press the Execute SQL statement in a new tab button ![vqb Execute SQL statement in a new tab button](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/execute_in_new_tab.png).

### Shortcuts
You can use the same shortcuts as in the SQL Editor to execute the Visual Query.

| Key                        | Description                            |
|----------------------------|----------------------------------------|
| Ctrl+Enter                 | Execute the SQL statement              |
| Ctrl+\ or Ctrl+Shift+Enter | Execute the SQL statement in a new tab |


## The Visual Query Builder symbols
The Visual Query Builder uses the following visual tools to display queries on the diagram:

### Table symbols

| Symbol | Description                                                         |
|--------|---------------------------------------------------------------------|
|![vqb pk](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_pk.png)        | Table Primary Key is bold and displayed at the top of the table.    |
|![vqb table alias](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_table_alias.png)        | Table Alias is used to shorten your Join Statement.                 |![vqb sorting](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_sorting.png)
|![vqb coloured header](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_table_header.png)        | Colored table header  marks the first table in your Join Statement. |
|![vqb colourless header](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_table_colourless_header.png)        | Colorless header  marks a joined table in your Join Statement.      |
|![vqb line](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_line.png)        | Line goes from the joined table to the first table.                 |

### Join symbols
Available Join types are described in the table below. The Visual Query Builder can show results only for those types of Joins that are supported by your database.

| Symbol | Description      |
|--------|------------------|
|![vqb Inner Join ](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/inner_join.png)        | Inner Join       |
|![vqb Left Join](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/left_join.png)        | Left Join        |
|![vqb Left Outer Join](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/left_outer_join.png)        | Left Outer Join  |
|![vqb Right Join](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/right_join.png)        | Right Join       |
|![vqb Right Outer Join](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/right_outer_join.png)        | Right Outer Join |
|![vqb Full Join](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/full_join.png)        | Full Join        |
|![vqb Full Outer Join](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/full_outer_join.png)        | Full Outer Join  |
|![vqb Cross Join](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/cross_join.png)        | Cross Join       |


## Settings
You can customize the diagram view using the bottom toolbar to make the work with the diagram easier.

![vqb_settings_menu](https://github.com/dbeaver/cloudbeaver/wiki/images/vqb/vqb_settings_menu.png)

* **Layout** updates the diagram view to display all of its objects in the most optimal way.

* **Zoom in** and **Zoom out** enlarges or shrinks the diagram view.

* **Settings** menu contains additional settings of the Visual Query Builder. Press the Settings button at the bottom toolbar to open it.

  * **Layout on update** enables Auto-layout feature. As soon as you add a new object to the diagram, the diagram view will automatically be updated to display all of its objects in the most optimal way.
  * **Show join type on entities** moves Join labels from lines into headers of joined tables.
  * **Show Type** adds information about column types into entities.
  * **Show Icons** adds icons of column types into entities.
  * **Notation** changes the representation of connection lines. Simple notation is set by default. You can change it to the IDEF1X language type.

## Visualization of an existing SQL query
If you write a JOIN statement by yourself and then want to convert it to the diagram view, just switch the SQL Editor with your statement to the Visual Query Builder.

**Note**: the Visual Query Builder can transform the syntax of your query, but it does not affect the query result in the Result set.