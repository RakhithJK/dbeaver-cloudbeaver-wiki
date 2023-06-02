## Features
* [Description](#description)
* [Creation](#creation)
* [Connection Form](#connection-form)

## Overview

### Description
You can add, edit, or remove shared database connections or database connection templates on the `Connection Management` page in administration.

![Connection Management](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/connection-management.png)

### Creation

![Custom](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/new_custom.png)

To establish a new connection, follow the steps below:

1. Click the `Add` button located on the top toolbar. This will open the connection creation form.
2. Fill out the fields in the form with the appropriate information.
3. Once all fields are completed, click `Create`.

Your new connection should be successfully created and it will appear at the top of the connection table.

### Connection Form
Below are the detailed steps to set the connection parameters:

1. Open the connection form. This can be done by clicking the `Add` button in the toolbar.
2. Fill in the appropriate information in the base connection parameters, driver settings, SSH tunnel, and access fields.
3. If you want to create a connection template, check the `Template` checkbox.
4. To verify the database connection, click the `Test Connection` button. If SSH is configured, the test will use it to establish the connection.
5. If the connection requires authentication, users will be prompted to enter their credentials. 
6. As an administrator, you can set and save these authentication parameters by checking the `Save Credentials` checkbox in the `Authentication` section. Doing so will allow any user with access to the connection to connect without needing to enter their credentials.

![Connection Form](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/new_form.png)

You can manage access to the database at the `Access` tab. You can select users or roles to provide access to.

![Connection Form](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/connection_management/new_form_access.png)

