There are several configuration files in CloudBeaver.

## Main server configuration 

The primary configuration file is `cloudbeaver.conf`. By default it is placed in the folder `/etc/cloudbeaver/`.  
But in most cases it is redefined for each server by the command line parameter `-web-config <config-file-path>`.  
The server configuration is in the JSONC format (JSON with comments and without redundant quotes). It can be parsed by most of the JSON parsers in lenient mode.  
Additionally, configuration parameters can be specified in the file `workspace/.data/.cloudbeaver.runtime.conf`. It is convenient because the workspace can be deployed as a shared docker volume. `.cloudbeaver.runtime.conf` has the same structure as `cloudbeaver.conf` but it has a higher priority than `cloudbeaver.conf`.   


Typical configuration:
```js
{
    server: {
        serverPort: 8978,
        serverHost: "localhost",
        serverName: "CloudBeaver Sample Server",

        // Paths are absolute or relative to the server root folder
        workspaceLocation: "workspace",
        contentRoot: "web",
        driversLocation: "drivers",

        rootURI: "/",
        serviceURI: "/api/",

        // Webapp configuration file
        productConfiguration: "conf/product.conf",

        expireSessionAfterPeriod: 600000,

        develMode: false,

        database: {
            url: "jdbc:h2:${workspace}/.data/cb.h2.dat",
            initialDataConfiguration: "conf/initial-data.conf",
            pool: {
                minIdleConnections: 4, 
                maxIdleConnections: 10,
                maxConnections: 100,
                validationQuery: "SELECT 1"
            }
        }
    },
    app: {
        anonymousAccessAllowed: true,
        anonymousUserRole: "user",
        supportsCustomConnections: false,
        publicCredentialsSaveEnabled: true,
        adminCredentialsSaveEnabled: true,
        resourceManagerEnabled: true,
        resourceQuotas: {
            dataExportFileSizeLimit: 10000000,
            resourceManagerFileSizeLimit: 500000,
            sqlMaxRunningQueries: 100,
            sqlResultSetRowsLimit: 100000,
            sqlResultSetMemoryLimit: 2000000,
            sqlTextPreviewMaxLength: 4096,
            sqlBinaryPreviewMaxLength: 261120
        },
        defaultNavigatorSettings: {
            showSystemObjects: true,
            showUtilityObjects: false,
            showOnlyEntities: false,
            mergeEntities: false,
            hideFolders: false,
            hideSchemas: false
        },
        plugins: {

        },
        enabledAuthProviders: [
            "local"
        ],
        enabledDrivers: [
            
        ],
        disabledDrivers: [
            "sqlite:sqlite_jdbc",
            "h2:h2_embedded"
        ]

    }

}
```

All paths can be absolute or are relative to the server start directory (or current directory).

### Server parameters:

Name|Description
---|---
serverPort | Port CloudBeaver server listens on
serverHost | The network interface CloudBeaver server binds to as an IP address or a hostname. If null or 0.0.0.0, then bind to all interfaces.
serverURL | Server address (full URL). Used to generate links and for third-party services integration.
workspaceLocation | Root folder for projects
contentRoot | Path to directory with static content
driversLocation | Optional path for driver jar files
rootURI | Web application URI prefix. `/` by default
serviceURI | Services API URI prefix (relative to rootURI). `/api/` by default.
productConfiguration | Path to product (web interface) configuration file (json)
develMode | When set to true extra debug, the information is printed in logs and GraphQL console is enabled on the server.
expireSessionAfterPeriod | Maximum idle time after which user's session will be closed.

#### Database configuration

Configures CloudBeaver database where it keeps users, credentials and permissions.  
In the section `server.database`:

Name|Description
---|---
driver | Database driver (e.g. `sqlite`, `h2_embedded`, `postgres-jdbc`, etc)
url | Database JDBC URL (e.g. `jdbc:postgresql://localhost:5432/cb`
user | Database user name
password | Database user password
initialDataConfiguration | Path to initial data file (json) that will be loaded on first server run

#### Database connection pool configuration

Configures connection pool to be used by the CloudBeaver database.  
In the section `server.database.pool`:

Name|Description
---|---
validationQuery | Query that will check the successful connection to the database
minIdleConnections | Minimum number of idle connections that should be kept in the pool
maxIdleConnections | Maximum number of idle connections that should be kept in the pool
maxConnections | Maximum number of idle and active connections that should be kept in the pool

#### Database Initial Data

Configures initial data containing administrator credentials and a list of roles and their permissions.  
Stored in a separate file, the path to which is specified in the section `server.database.initialDataConfiguration`:

Name|Description
---|---
adminName | Username for administrator
adminPassword  | Password for administrator
roles  | List of initial roles

Roles schema

Name|Description
---|---
roleId | Id for the role
name | Name for the role
description | Role description
permissions | Set of available permissions for the role

Configuration example:

```js
{
    adminName: "cbadmin",
    adminPassword: "cbadmin20",
    roles: [
        {
            roleId: "admin",
            name: "Admin",
            description: "Administrative access. Has all permissions.",
            permissions: ["public", "admin"]
        },
        {
            roleId: "user",
            name: "User",
            description: "Standard user",
            permissions: ["public"]
        }
    ]
}
```

### Application parameters:

In the section `app`:

Name|Description
---|---
anonymousAccessEnabled | Allows anonymous access. Anonymous users work with the role `anonymousUserRole`.
anonymousUserRole  | A role that will be assigned to the anonymous user, `user` by default.
authenticationEnabled | Enables users' authentication. If disabled, then only anonymous access is allowed.
supportsCustomConnections | Allows users to create custom connections to any databases. Otherwise only the CB administrator can create/edit connections.
publicCredentialsSaveEnabled | Allows you to save user database credentials in a local cache.
adminCredentialsSaveEnabled | Allows you to save global database credentials in a local cache.
redirectOnFederatedAuth | When there is only one federation authentication configuration, then redirect to it automatically.
forwardProxy | Identifies the originating IP address and other headers of a client connecting to a web server through an HTTP proxy.
enabledDrivers | List of drivers that are allowed to be used, if the list is empty - all drivers are allowed.
disabledDrivers  | List of drivers that are prohibited for use, if the list is empty - all drivers are allowed.
enableReverseProxyAuth  | Enabling reverse proxy authorization mechanism for more details can be found [here](https://github.com/dbeaver/cloudbeaver/wiki/Reverse-proxy-header-authentication).
defaultAuthProvider | Provider that will be used for authorization by default.
enabledAuthProviders | List of allowed authorization providers, if the property is absent - all providers are allowed.
defaultNavigatorSettings | Default database navigator settings.

#### Resource quotas

You can configure the following resource quotes in the section `app.resourceQuotas`:

Name|Description
---|---
dataExportFileSizeLimit | Maximum file size for data export operation (in bytes)
resourceManagerFileSizeLimit | Maximum file size saved in the resource manager (in bytes)
sqlMaxRunningQueries | Maximum number of simultaneous queries for a single user session. Includes data read queries (i.e. table data view)
sqlResultSetRowsLimit | Maximum number of rows to select from a table or query
sqlTextPreviewMaxLength | Maximum size for text file shown in value panel (in bytes)
sqlBinaryPreviewMaxLength| Maximum size for binary file shown in value panel (in bytes)

#### Navigator settings

You can configure the following properties in the section `app.defaultNavigatorSettings`:

Name|Description
---|---
showSystemObjects | Show system objects.
showUtilityObjects | Show "utility" objects.
showOnlyEntities | Show only schemas and tables.
mergeEntities | Show all types of database objects in one list (tables, sequences, etc.).
hideFolders | Hide folders like "Tables", "Schemas", "Columns", etc.
hideSchemas | Do not show schemas (all tables in one list).

# Automatic server configuration

On the first start CloudBeaver server will show administrator interface for server configuration.  
In some cases the server must be configured automatically (e.g. when it is run in the Kubernetes environment).  
The following parameters must be specified in the configuration:

Name|Description|Example
---|---|---
CB_SERVER_NAME | Server name | `Test Server`
CB_SERVER_URL | Server base URL | `https://cloudbeaver.domain.com:10000/`
CB_ADMIN_NAME | Administrator user name | `admin`
CB_ADMIN_PASSWORD | Administrator user password | `S0mePazzworD`

These parameters can be specified in:
- OS environment variables 
- configuration file `.cloudbeaver.auto.conf` which must be placed in the same location as the `cloudbeaver.conf` file.  

## Datasources configuration 

You can find a detailed description at [[here|Configuring-server-datasources]]

## Using environment variables
You can use references on environment variables in most server configuration properties.
For example:

```js
{
    server: {
        serverPort: ${cb.port},
        serverHost: "${cb.host}",
        serverName: "CloudBeaver Server",

        rootURI: "${cb.prefix}",
        serviceURI: "/api/",

        expireSessionAfterPeriod: ${cb.expire-time},
    }
}
```
