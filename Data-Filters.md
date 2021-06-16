You can apply custom filters to table contents or query results. There are several ways in which you can filter data in the table.

One of the ways is to use the filter field above the table next to the top toolbar. To filter data, enter an SQL expression into the field and click the Apply filter criteria button ![Apply Button](https://github.com/dbeaver/cloudbeaver/wiki/images/Apply-filter-criteria-button.png) next to the field or press <kbd>Enter</kbd>.

![Filter Top Bar](https://github.com/dbeaver/cloudbeaver/wiki/images/Filter-criteria.png)
 
You can apply ready-to-use SQL expressions or SQL expression templates via the context menu. To select a ready SQL expression or a template, select or focus cell and press Cell context button ![Context Button](https://github.com/dbeaver/cloudbeaver/wiki/images/Context-button.png), then click **Filters** -> **Cell value** on the context menu and then choose one of the expressions.

![Filter Expressions](https://github.com/dbeaver/cloudbeaver/wiki/images/Context-constructed-filters.png)

The data updates dynamically. To remove a filter, click **Filters** -> **Delete filter for ..**. If you want to delete all filters, click **Filters** -> **Reset all filters**. You can also delete filters by clicking Reset filter criteria button ![Reset Filter Button](https://github.com/dbeaver/cloudbeaver/wiki/images/Reset-filter-criteria-button.png) in the top toolbar.

![Reset Filter](https://github.com/dbeaver/cloudbeaver/wiki/images/Context-filters.png)

Another tool for managing the data appearance is the column headers. In the data table, every column header contains two elements which each has its own function: Data (column) type icon, column name and ordering icon.

![Column Header](https://github.com/dbeaver/cloudbeaver/wiki/images/Column-header.png)

* Clicking the column name or column type allows you to select the whole column.
* Clicking the ordering icon allows you to order the data in the column in ascending or descending order - see the 'Ordering Data in Columns' section, further in this article

## Ordering Data in Columns
You can order data in columns in one of the following ways:
1. Click the ordering icon ![Ordering Icon](https://github.com/dbeaver/cloudbeaver/wiki/images/Order-unknown.png) in the header of the column.

   ![Ordering states](https://github.com/dbeaver/cloudbeaver/wiki/images/Order-states.png) 

   The icon has three states:  
   * Clicking once establishes ascending order ![Ascending Order](https://github.com/dbeaver/cloudbeaver/wiki/images/Order-ascending.png)  
   * Clicking a second time changes the order to descending ![Descending Order](https://github.com/dbeaver/cloudbeaver/wiki/images/Order-descending.png)  
   * Clicking a third time removes the ordering from the column ![Ordering Icon](https://github.com/dbeaver/cloudbeaver/wiki/images/Order-unknown.png)  

To order data by several columns, go column by column, holding the <kbd>ctrl</kbd> (windows) or <kbd>cmd</kbd> (mac) button, setting the order with the Ordering icon, starting from the column by which you want to order data first.

2. Open context menu, click **Sorting**. Choose from several ordering states we've mentioned before.
When we choose ordering state from the context menu, there is no need to hold <kbd>ctrl</kbd> or <kbd>cmd</kbd> button to order data by multiple columns. 

![Reset Filter Button](https://github.com/dbeaver/cloudbeaver/wiki/images/Reset-filter-criteria-button.png)

To reset the column data ordering to its initial state, open Cell context menu and click **Sorting -> Disable**. 
If you want to reset all data ordering, open Cell context menu, then click **Sorting -> Disable all**. You can also click Ordering icon in the header of the any column to reset all data ordering.

![Ordering states](https://github.com/dbeaver/cloudbeaver/wiki/images/Context-order-states.png)