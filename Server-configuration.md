There are several configuration files in CloudBeaver.

## Main server configuration 

Primary configuration file is `cloudbeaver.conf`. By default it is placed in folder `/etc/cloudbeaver/`.  
But in most cases it is redefined for each server by command line parameter `-web-config <config-file-path>`.

Typical configuration:
```js
{
    server: {
        serverPort: 8978,
        serverName: "CloudBeaver Sample Server",

        workspaceLocation: "workspace",
        contentRoot: "web",
        driversLocation: "drivers",

        rootURI: "/",
        serviceURI: "/dbeaver/",

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
productConfiguration | Path to product (web interface) configuration file (json)
develMode | When set to true extra debug information is printed in logs and GraphQL console is enabled on server.

## Datasources configuration 

You can find detailed description [[here|Configuring-server-datasources]]