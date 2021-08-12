## Features
* [Initial server configuration](#initial-server-configuration)
* [Connection management](#entering-administration-page)
* [User management](#user-management)
* [Server configuration](#server-configuration)

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

   ![Screenshot 2021-08-12 at 12 56 22](https://user-images.githubusercontent.com/51405061/129177762-bcf6dd45-6987-4355-ae81-cf85dad30d4f.png)

2. Connection creation

   Click on Add icon in tools bar to open connection creation wizard:

   ![Screenshot 2021-08-12 at 13 01 48](https://user-images.githubusercontent.com/51405061/129178401-5874f1c9-b737-4b0e-a24a-1f3dcb0cc51c.png)

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

   Click on Add icon in tools bar to open user creation form:
   
   ![Screenshot 2021-08-12 at 13 05 30](https://user-images.githubusercontent.com/51405061/129178948-bd566239-0247-4fcb-9157-9a1a97a035ed.png)

   You can set user credentials and roles, also you can configure connections access.

   Connection access can be provided via user role, or directly.

3. User edit

   User can be edited after creation for that in users table click on user name or angle icon.

4. User deletion

   User can be deleted for that select users in table and click on trash icon in tools bar

### Server configuration
In administration page select *Server configuration* tab. On *Server configuration* tab you can edit base application settings

   ![Screenshot 2021-08-12 at 13 08 13](https://user-images.githubusercontent.com/51405061/129179301-3ff86420-8521-4a53-ad47-ac48901cd9d2.png)