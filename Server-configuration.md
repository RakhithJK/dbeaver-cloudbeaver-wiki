There are several configuration files in Cloudbeaver.

## Main server configuration 

Primary configuration file is `cloudbeaver.conf`. By default it is placed in folder `/etc/cloudbeaver/`.  
But in most cases it is redefined for each server by command line parameter `-web-config <config-file-path>`.

Typical configuration:
```preeprties
ServerPort = 8978
ServerName = Cloudbeaver Sample Server

WorkspaceLocation = workspace
ContentRoot = web
DriversLocation = drivers

ProductConfiguration = conf/product.js

DevelMode = false
```

All paths can be absolute or are relative to the server start directory (or current directory).
Parameters:

Name|Description
---|---
ServerPort | Port for Cloudbeaver web server
WorkspaceLocation | Root folder for projects
ContentRoot | Path to directory with static content
DriversLocation | Optional path for driver jar files
ProductConfiguration | Path to product (web interface) configuration file (json)
DevelMode | When  set to true extra debug information is printed in logs and GraphQL console is enabled on server.

## Datasources configuration 

You can find detailed description [[here|Configuring-server-datasources]]