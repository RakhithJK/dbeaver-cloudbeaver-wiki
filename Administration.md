## Features
* [Initial server configuration](#initial-server-configuration)
* [Connection management](#entering-administration-page)
* [User management](#user-management)
* [Server configuration](#server-configuration)

## Overview

### Initial server configuration
The first time you run the application, the application will require an initial configuration. On the initial configuration you will need to configure some things:

1. Server configuration - base application settings such as: administrator account, server info and   base application behavior

   ![Server configuration](https://github.com/dbeaver/cloudbeaver/wiki/images/initial-config-server-configuration.png)

2. Database connections - in that step you can add some common connections for yours databases

   ![Database connections](https://github.com/dbeaver/cloudbeaver/wiki/images/initial-config-database-connections.png)
   
   The application will try to find databases on the host machine, so you can simply add existing databases or enter hosts to search in (hosts can be divided by spaces or comma):

   ![Connection configuration](https://github.com/dbeaver/cloudbeaver/wiki/images/initial-config-database-connections-postgresql.png)

   ![Connections list](https://github.com/dbeaver/cloudbeaver/wiki/images/initial-config-database-connections-list.png)

### Entering administration page
After the initial server configuration, you can login as an administrator:
* If the authentication is enabled: *Settings (top right corner, the cog icon) > login*
* Another option is to enter `/#/admin` page
 
  ![Login form](https://github.com/dbeaver/cloudbeaver/wiki/images/login-form.png)

After successful authentication with the administrator account, you can enter *Administration* page:
* via settings *Settings (top right corner, the cog icon) > Administration*
* Directly go to `/#/admin` page

### Connection management
On the administration page, select the *Connection Management* tab. On the *Connection Management* tab you can create or delete connections, and configure connections (connection settings, users access).

1. Connection list

   ![Screenshot 2021-08-12 at 12 56 22](https://user-images.githubusercontent.com/51405061/129177762-bcf6dd45-6987-4355-ae81-cf85dad30d4f.png)

2. Connection creation

   Click on the Add icon on the tools bar to open the connection creation wizard:

   ![Screenshot 2021-08-12 at 13 01 48](https://user-images.githubusercontent.com/51405061/129178401-5874f1c9-b737-4b0e-a24a-1f3dcb0cc51c.png)

   The connection can be created from the database driver or from databases searched in the entered hosts (hosts can be divided by spaces or comma).

   Before adding a connection you can test the connection. For that, you should fill in the authentication parameters (if needed).
   If the *Template* is checked, then users can add that connection from *Connection > From Template* otherwise the connection will be presented in the navigation tree if the user has access to that connection (directly or by role). Connection access can be configured on the connection *Access* tab.

   The connection authentication parameters can be filled in by the administrator and saved for all users, so they do not need to enter the connection credentials.

3. Connection edit

   The connection can be edited after creation. In the connections table click on the connection name or the angle icon.

4. Connection deletion

   The connection can be deleted. Select the connections in the table and click on the trash icon on the tools bar.

### User management
On the administration page, select the *Users* tab. On the *Users* tab you can create or delete, and create or edit users.

1. User list

   ![User list](https://github.com/dbeaver/cloudbeaver/wiki/images/administration-users.png)

2. User creation

   Click on the Add icon on the tools bar to open the user creation form:
   
   ![Screenshot 2021-08-12 at 13 05 30](https://user-images.githubusercontent.com/51405061/129178948-bd566239-0247-4fcb-9157-9a1a97a035ed.png)

   You can set the user credentials and roles. You can also configure the connections access.

   Connection access can be provided via a user role, or directly.

3. User edit

   The user can be edited after the creation. In the users table, click on the user name or the angle icon.

4. User deletion

   The User can be deleted. Select the users in table and click on the trash icon on the tools bar.

### Server configuration
On the administration page select the *Server configuration* tab. On the *Server configuration* tab you can edit the base application settings.

   ![Screenshot 2021-08-12 at 13 08 13](https://user-images.githubusercontent.com/51405061/129179301-3ff86420-8521-4a53-ad47-ac48901cd9d2.png)