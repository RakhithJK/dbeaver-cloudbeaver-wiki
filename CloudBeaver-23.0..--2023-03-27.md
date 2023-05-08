### CloudBeaver 23.0.4 - 2023-05-08

-  Improvements based on GitHub user requests have been added:
 - error when running SQL with semicolon has been fixed;
 - option to increase the maximum size of text files displayed in the value panel (using the sqlTextPreviewMaxLength parameter) has been added;
 - support for custom logging configuration has been added. An external configuration file can be used instead of the default configuration.
-  Different bugs have been fixed.

### CloudBeaver 23.0.3 - 2023-04-24

-  New grouping panel menu was added in the Data Viewer. This panel extracts unique values from the database column for count. Users can drag and drop the column to the grouping panel and get the results immediately. Sorting, filtering and exporting of the results are available on the Grouping panel.

-  Different bugs have been fixed.

### CloudBeaver 23.0.2 - 2023-04-10

-  In the SQL editor, when the cursor goes back on the query, the previous hints are displayed.
-  CloudBeaver has the option to connect to H2 database version 2.
-  The internal CloudBeaver database is upgraded to the newest H2 version 2 to avoid vulnerability issues. The database will be safely upgraded automatically for the servers with default configurations. You can perform this upgrade manually if you have a custom configuration for this database in your infrastructure.
-  Different bugs have been fixed.

### CloudBeaver 23.0.1 - 2023-03-27

-  If there is an error in saving the data, the tab for the chosen connection dialog will stay open to allow corrections.
-  Different bugs have been fixed.