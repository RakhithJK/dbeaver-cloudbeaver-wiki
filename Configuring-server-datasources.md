## Configuring server "predefined" connections

See [[Connection configuration|Connection-configuration]] for descriptions of the different connection types.

### Overview 

The CloudBeaver server may have a set of pre-configured database connections. 
This configuration is stored on a server and cannot be changed by end-users.

An End-user may choose one of the pre-configured connections on the main CloudBeaver toolbar. Then the user has to provide a username/password in order to connect to the pre-configured datasource. No other parameters are needed.

See [[Server configuration|Server-configuration]] for information about the server and workspace configuration.

### Datasources configuration file

All project-level configurations are stored in the folder, `${CLOUDBEAVER_WORKSPACE}/GlobalConfiguration/.dbeaver`.
Datasources are configured in the file, `data-sources.json`.

It has the same format as [DBeaver](https://github.com/dbeaver/dbeaver) datasources configuration file.
In version 1.0 CloudBeaver does not support UI for datasources configuration (mostly because it is quite complicated).

You can create this configuration in DBeaver and then copy it to your server configuration folder. Then you can patch the configuration manually by editing the configuration json.