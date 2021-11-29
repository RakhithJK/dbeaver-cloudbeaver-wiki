## Features
* [Description](#description)
* [Creation](#creation)
* [Connection Form](#connection-form)

## Overview

### Description
You can add, edit, or remove shared database connections or database connection templates at the `Connection Management` page in administration.

![Connection Management](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/connection-management.png)

### Creation
Click the `Add` button in the top toolbar to open the connection creation form.

![Search](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/new_search.png)
You can use the `Search` tab to find databases on the cloudbeaver host machine or provided host. You can choose database type if several databases can be hosted on the same port. You can write several hosts to search on: `localhost yourhost.com` or `localhost, yourhost.com`. Click on the connection in the list to open the creation form (where you can select database type).

![Custom](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/new_custom.png)
You can use the `Custom` tab to create a connection for the specified database or driver. You can search databases by name.

### Connection Form
You can set base connection parameters, driver settings, SSH tunnel, and access in the connection form.
A connection template will be created if the `Template` checkbox is checked.
To check the connection to the database, click on the `Test connection` button; if SSH configured, it will be used to test the connection.
Users will be asked to enter credentials if the connection requires authentication. An administrator can set authentication parameters and save them (`Save credentials` checkbox in `Authentication` section); in that case, any user that has access to a connection will be able to connect without entering credentials.

![Connection Form](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/new_form.png)

You can manage access to the database at the `Access` tab. You can select users or roles to provide access to.

![Connection Form](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/new_form_access.png)

