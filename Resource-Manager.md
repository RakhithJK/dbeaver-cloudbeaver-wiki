# Overview

The Resource Manager allows users to store and manage scripts in the CloudBeaver server file system. Each user has a personal project where saved scripts are stored. Other users do not have access to it. 
The Resource Manager is only available to logged users. Anonymous users may save scripts on a local machine.

Administrators can disable the feature in the Server Settings in the Administration menu.

### Opening the Resource Manager
To open the Resource Manager select it in the Tools menu.

![Resource Manager Open](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/rm_open.png)

The Resource Manager panel will appear to the right of the SQL Editor. 
The panel contains the list of saved user’s scripts in ascending order. Every script has the context menu with tools.

![Resource Manager](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/rm.png)

### Saving a script
To save an SQL script to the Resource Manager, press the Save button ![Resource Manager Save button](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/rm_save.png) on the left SQL Editor toolbar. The script will be saved to the user project in the CloudBeaver server and the script name will appear in the Resource Manager panel.

Once a script is saved in the Resource Manager, a user should not save it manually any more, because auto-save mode begins to work for the script:
* every second when any changes have been made in it;
* every time when the SQL Editor with the script has been closed.

### Opening a script
To open a saved script double click the script name in the Resource Manager panel or select Open in the script context menu. 

![Resource Manager context menu](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/rm_context_menu.png)

The script will be opened in a separate SQL Editor and its name will be displayed on the SQL Editor tab. By default the opened script is not connected to any database. To set a connection, select a connection name in the SQL Editor top toolbar. 

### Deleting a script
To delete a script from the Resource Manager select Delete in the script context menu in the Resource Manager panel. The script will disappear from the panel and will be deleted from the CloudBeaver server. The SQL Editor with the script will also be closed if it has been opened.
The deleted script cannot be restored.

### Script size limit
You can configure the size limit for scripts in the Resource Manager. This can be useful if you need to control the amount of space on the CloudBeaver server. The limit also helps to improve the application performance, because opening big scripts can take quite a long time. If a user is saving a large script, he will see a message that the file size has been exceeded and the script will not be saved. [This article describes how to configure the limit](https://github.com/dbeaver/cloudbeaver/wiki/Server-configuration#resource-quotas).