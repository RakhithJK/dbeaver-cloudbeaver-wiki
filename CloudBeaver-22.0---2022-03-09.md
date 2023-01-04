### **CloudBeaver 22.0 - 2021-03-09**

Changes since 21.0:

* Administration:
    * role management has been added;
    * access management for users and connections is improved;
    * specific drivers can be excluded from the connection list;
    * the instruction to update the CloudBeaver version has been added.
* Data Editor:
    * users can add, delete and duplicate rows;
    * tables can be exported with applied filters and sorting;
    * the SQL script preview is available after making changes and before saving or discarding them;
    * arrays and XML values can be edited;
    * it is possible to edit Boolean values as checkboxes;
    * hotkeys are added for table editing;
    * read-only columns and tables are marked;
    * confirmation is required to close or refresh a table with unsaved changes;
    * links to the web pages can be opened from the tables;
    * new actions are available from the context menu:
        * filtering,
        * ordering,
        * cell editing;
    * the Value panel:
        * support for different formats has been added,
        * links to the pictures are automatically transformed to the pictures,
        * radio buttons have been added to edit Boolean values.
* SQL Editor:
    * the SQL Editor tabs can be renamed;
    * SQL formatting is available;
    * scripts can be downloaded and uploaded to an external file;
    * option to run SQL scripts has been implemented;
    * query execution plan is now available;
    * auto-complete for the SQL dialects works automatically;
    * parsing of scripts with delimiters has been improved;
    * the SQL Editor can be opened in a separate browser tab;
    * database logos are displayed in the top menu selector.
* Metadata Editor:
    * objects DDL can be saved to an external file;
    * objects can be deleted and renamed;
    * SQL Scripts generation is available in the objects’ context menu;
    * the new tab’s context menu allows users to close all opened tabs or a group of tabs.
* Database Navigator:
    * the new menu allows users to:
        * filter objects in the Navigator tree,
        * collapse the Navigator tree to the root level,
        * synchronise the active Metadata Editor with the element in the Database Navigator;
    * private and shared connections are divided into different groups;
    * the Navigator tree view, Simple or Advanced, can be set for every user separately;
    * objects can be deleted and renamed;
    * SQL Scripts generation is available for objects;
    * users will be informed if the number of displayed elements is limited.
* Connections:
    * SSH public key support has been added;
    * the database and SSH credentials can be entered to test connections;
    * read-only connections are marked in the connection form;
    * it is possible to show and hide password in the connection dialog;
    * DB2 iSeries driver has been added.
* Log viewer:
    * users can see detailed information for errors in the panel.
* New Profile menu allows users to:
    * see information about the current user;
    * change the password for the current user.
* Local configuration:
    * the following features can be disabled:
        * table data editing,
        * table data export,
        * the possibility to edit database objects;
    * driver access to the file system can be limited;
    * specific IP addresses can be set for the CloudBeaver instance;
    * the following limits can be set:
        * the size of exported files,
        * the number of fetched table rows,
        * the number of executable queries at the same time;
    * user access information can be stored in a local database.
* Command line parameters:
    * Xms and Xmx environment variables can be set for the CloudBeaver instance;
    * the possibility to skip the Initial server configuration is now available.
* Initial server configuration has been simplified.
* The dialog with available shortcuts can be opened from the top menu.
* Theme settings can be configured and saved for every user separately.
* User IDs have been added to the logs.
* Chinese UI localization is now supported.
* Session expiration notifications have been improved.
* A lot of bug fixes, enhancements and improvements have been made.