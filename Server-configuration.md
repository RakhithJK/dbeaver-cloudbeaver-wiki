There are several configuration files in CloudBeaver.

## Main server configuration 

The primary configuration file is `cloudbeaver.conf`. By default it is placed in folder `/etc/cloudbeaver/`.  
But in most cases it is redefined for each server by the command line parameter `-web-config <config-file-path>`.  
The server configuration is in JSONC format (JSON with comments and without redundant quotes). It can be parsed by most of the JSON parsers in lenient mode.  
Additionally configuration parameters can be specified in the file `workspace/.data/.cloudbeaver.runtime.conf`. It is convenient because workspace can be deployed as a shared docker volume. `.cloudbeaver.runtime.conf` has the same structure as `cloudbeaver.conf` but it has higher priority than `cloudbeaver.conf`.   


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

        develMode: false
    },
    app: {
        anonymousAccessAllowed: true,
        anonymousUserRole: "user"
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
publicCredentialsSaveEnabled | Allows to save user database credentials in local cache
adminCredentialsSaveEnabled | Allows to save global database credentials in local cache

# Automatic server configuration

On the first start CloudBeaver server will show administrator interface for server configuration.  
In some cases server must be configured automatically (e.g. when it is run in Kubernetes environment).  
Following parameters which must be specified in the configuration:

Name|Description|Example
---|---|---
CB_SERVER_NAME | Server name | `Test Server`
CB_SERVER_URL | Server base URL | `https://cloudbeaver.domain.com:10000/`
CB_ADMIN_NAME | Administrator user name | `admin`
CB_ADMIN_PASSWORD | Administrator user password | `S0mePazzworD`

These parameters can be specified in:
- OS environment variables 
- configuration file `.cloudbeaver.auto.conf` which must be placed in the same location as `cloudbeaver.conf` file.  

## Datasources configuration 

You can find a detailed description [[here|Configuring-server-datasources]]