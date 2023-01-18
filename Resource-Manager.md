# Overview

The Resource Manager allows users to store and manage scripts in the CloudBeaver server file system. Scripts can be saved in both projects, the Private or the Shared, and available to every user who has access to this project. 

Each user has the Private project and can create, edit and delete scripts in it. Other users do not have access to this project. 

Administrators can also create and manage scripts in the Shared project. All users with access to this project can see, open and run the project scripts.  
Scripts can be associated with a specific connection. When a user opens such a script, the specified connection is displayed in the SQL Editor top toolbar and the user can immediately execute the script for the connection. **Note**: scripts can only be associated with connections from the same project.

The Resource Manager is only available to logged users. Anonymous users may save scripts on a local machine.

Administrators can deactivate the Resource Manager in the Server Settings in the Administration. The Resource Manager panel disappears from the CloudBeaver interface and users don’t have access to scripts on the server. 


### Opening the Resource Manager
To open the Resource Manager select it in the Tools menu.

![sql_scripts_manager_open](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/sql_scripts_manager_open.png)

The Resource Manager panel will appear to the right of the SQL Editor. 
The panel contains the list of saved user’s scripts in ascending order. Every script has the context menu with tools.

![sql_scripts_manager](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/sql_scripts_manager.png)

### Saving a script
To save an SQL script to the Resource Manager, press the Save button ![Resource Manager Save button](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/rm_save.png) on the left SQL Editor toolbar:

For users: the script will be saved to the Private project in the CloudBeaver server.

For administrators: 
* if a connection for the script is not selected, the script will be saved to the project selected by the administrator in the pop up dialog box. 
 
![sql_scripts_manager_save](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/sql_scripts_manager_save.png)

* if a connection for the script is selected, the script will be saved to the project where the connection is stored.

The script name will appear in the Resource Manager panel under the project name.

Once a script is saved in the Resource Manager, all future changes will automatically be saved in it:
* each time any changes have been made in it
* every time when the SQL Editor with the script has been closed.

Specifying  a connection for a script
If necessary, when you want to specify a connection, just select a connection and a schema in the SQL Editor top toolbar for the script. The script will use this connection the next time the user opens it.
To change the connection, select another one in the SQL Editor top toolbar. The changes will be saved automatically.
To remove the connection, disconnect from the database in the Navigator tree and do not restore the connection for the script.

### Opening a script
To open a saved script, double click the script name in the Resource Manager panel or select Open in the script context menu.  

![sql_scripts_manager_context_menu](https://github.com/dbeaver/cloudbeaver/wiki/images/resource_manager/sql_scripts_manager_context_menu.png)

The script will be opened in a separate SQL Editor and its name will be displayed on the SQL Editor tab. If a connection has not  been specified for the script, users will need to select a connection name in the SQL Editor top toolbar before execution. 

### Deleting a script
To delete a script from the Resource Manager, select Delete in the script context menu in the Resource Manager panel. The script will disappear from the panel and will be deleted from the CloudBeaver server. The SQL Editor with the script will also be closed if it has been opened.
The deleted script cannot be restored.
Scripts from the Shared project can only be deleted by the administrators.

### Script size limit
You can configure the size limit for scripts in the Resource Manager. This can be useful if you need to control the amount of space on the CloudBeaver server. The limit also helps to improve the application performance, because opening big scripts can take quite a long time. If a user is saving a large script, they will see a message that the file size has been exceeded and the script will not be saved. [This article describes how to configure the limit](https://github.com/dbeaver/cloudbeaver/wiki/Server-configuration#resource-quotas).