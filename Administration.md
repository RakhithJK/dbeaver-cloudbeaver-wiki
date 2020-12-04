# Administration

## Features
* Initial server configuration
  1. Server configuration
  2. Database connection 
* Connection management
  1. Connection list
  2. Connection creation
  3. Connection edit
  4. Connection deletion
* User management
  1. User list
  2. User creation
  3. User edit
  4. User deletion
* Server configuration

## Overview

### Initial server configuration
First time you run application application will require initial configuration. On initial configuration you will configure some things:

1. Server configuration - base application settings such as: administrator account, server info and   base application behavior

   ![Server configuration](https://github.com/dbeaver/cloudbeaver/wiki/images/initial-config-server-configuration.png)

2. Database connections - on that step you can add some common connections for yours databases

   ![Database connections](https://github.com/dbeaver/cloudbeaver/wiki/images/initial-config-database-connections.png)
   
   Application will try to find databases on the host machine, so you can simply add existed databases or enter hosts to search in (hosts can be divided by spaces or comma):

   ![Connection configuration](https://github.com/dbeaver/cloudbeaver/wiki/images/initial-config-database-connections-postgresql.png)

   ![Connections list](https://github.com/dbeaver/cloudbeaver/wiki/images/initial-config-database-connections-list.png)

### Entering administration page
After initial server configuration you can login as administrator:
* If authentication enabled: *Settings (top right corner, the cog icon) > login*
* Another way is enter `/#/admin` page

  ![Login form](https://github.com/dbeaver/cloudbeaver/wiki/images/login-form.png)

After successful authentication with administrator account you can enter *Administration* page:
* via settings *Settings (top right corner, the cog icon) > Administration*
* Directly go to `/#/admin` page

### Connection management
In administration page select *Connection Management* tab. On *Connection Management* tab you can create or delete connections, configure connection (connection settings, users access).

1. Connection list

   ![Connection list](https://github.com/dbeaver/cloudbeaver/wiki/images/administration-connection-management.png)

2. Connection creation

   Click on plus icon in tools bar to open connection creation wizard:

   ![Connection creation](https://github.com/dbeaver/cloudbeaver/wiki/images/administration-connection-managment-creation.png)

   Connection can be created from database driver or from databases searched in entered hosts (hosts can be divided by spaces or comma).

   Before adding connection you can test connection, for that you should fill authentication parameters (if needed).
   If *Template* is checked then users can be able to add that connection from *Connection > From Template* otherwise connection will be presented in navigation tree if user has access for that connection (directly or by role). Connection access can be configured on connection *Access* tab.

   Connection authentication parameters can be filled by administrator and saved for all users, so they don't need to enter connection credentials.

3. Connection edit

   Connection can be edited after creation for that in connections table click on connection name or angle icon.

4. Connection deletion

   Connection can be deleted for that select connections in table and click on trash icon in tools bar

### User management
In administration page select *Users* tab. On *Users* tab you can create or delete, create or edit users.

1. User list

   ![User list](https://github.com/dbeaver/cloudbeaver/wiki/images/administration-users.png)

2. User creation
   Click on plus icon in tools bar to open user creation form:
   
   ![User creation](https://github.com/dbeaver/cloudbeaver/wiki/images/administration-users-creation.png)

   You can set user credentials and roles, also you can configure connections access.

   Connection access can be provided via user role, or directly.

3. User edit

   User can be edited after creation for that in users table click on user name or angle icon.

4. User deletion

   User can be deleted for that select users in table and click on trash icon in tools bar

### Server configuration
In administration page select *Server configuration* tab. On *Server configuration* tab you can edit base application settings

![Server configuration](https://github.com/dbeaver/cloudbeaver/wiki/images/administration-server-configuration.png)

