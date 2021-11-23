There are several configuration files in CloudBeaver.

## Main server configuration 

The primary configuration file is `cloudbeaver.conf`. By default it is placed in the folder `/etc/cloudbeaver/`.  
But in most cases it is redefined for each server by the command line parameter `-web-config <config-file-path>`.  
The server configuration is in JSONC format (JSON with comments and without redundant quotes). It can be parsed by most of the JSON parsers in lenient mode.  
Additionally, configuration parameters can be specified in the file `workspace/.data/.cloudbeaver.runtime.conf`. It is convenient because the workspace can be deployed as a shared docker volume. `.cloudbeaver.runtime.conf` has the same structure as `cloudbeaver.conf` but it has a higher priority than `cloudbeaver.conf`.   


Typical configuration:
```js
{
    server: {
        serverPort: 8978,
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
            url: "jdbc:h2:${workspace}/.data/cb.h2.dat"
            initialDataConfiguration: "conf/initial-data.conf",
            pool: {
                maxConnections: 100
            }
        }
    },
    app: {
        anonymousAccessAllowed: true,
        anonymousUserRole: "user",
        supportsCustomConnections: false,

        resourceQuotas: {
            dataExportFileSizeLimit: 10000000,
            sqlMaxRunningQueries: 3,
            sqlResultSetRowsLimit: 100000,
            sqlResultSetMemoryLimit: 2000000
        },
        plugins: {

        }

    }

}
```

All paths can be absolute or are relative to the server start directory (or current directory).
Parameters:

Name|Description
---|---
serverPort | Port for CloudBeaver web server
workspaceLocation | Root folder for projects
contentRoot | Path to directory with static content
driversLocation | Optional path for driver jar files
rootURI | Web application URI prefix. `/` by default
serviceURI | Services API URI prefix (relative to rootURI). `/api/` by default.
productConfiguration | Path to product (web interface) configuration file (json)
develMode | When set to true extra debug, the information is printed in logs and GraphQL console is enabled on the server.
anonymousAccessEnabled | Allows anonymous access. Anonymous users work with the role, 'User'.
authenticationEnabled | Enables users' authentication. If disabled, then only anonymous access is allowed.
supportsCustomConnections | Allows users to create custom connections to any databases. Otherwise only the CB administrator can create/edit connections.
publicCredentialsSaveEnabled | Allows you to save user database credentials in a local cache
adminCredentialsSaveEnabled | Allows you to save global database credentials in a local cache

### Database configuration

Configures CloudBeaver database where it keeps users, credentials and permissions.
In the section `database`:

Name|Description
---|---
driver | Database driver (e.g. `sqlite`, `h2_embedded`, `postgres-jdbc`, etc)
url | Database JDBC URL (e.g. `jdbc:postgresql://localhost:5432/cb`
user | Database user name
password | Database user password

### Resource quotas

You can configure the following resource quotes:

Name|Description
---|---
dataExportFileSizeLimit | Maximum file size for data export operation (in bytes)
sqlMaxRunningQueries | Maximum number of simultaneous queries for a single user session. Includes data read queries (i.e. table data view)
sqlResultSetRowsLimit | Maximum number of rows to select from a table or query

# Automatic server configuration

On the first start CloudBeaver server will show administrator interface for server configuration.  
In some cases the server must be configured automatically (e.g. when it is run in Kubernetes environment).  
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

You can find a detailed description [[here|Configuring-server-datasources]]