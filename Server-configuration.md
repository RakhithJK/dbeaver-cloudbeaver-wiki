There are several configuration files in CloudBeaver.

## Main server configuration 

The primary configuration file is `cloudbeaver.conf`. By default it is placed in folder `/etc/cloudbeaver/`.  
But in most cases it is redefined for each server by the command line parameter `-web-config <config-file-path>`.  
The server configuration is in JSONC format (JSON with comments and without redundant quotes). It can be parsed by most of the JSON parsers in lenient mode.  

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

## Datasources configuration 

You can find a detailed description [[here|Configuring-server-datasources]]