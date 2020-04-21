## Configuring server "predefined" connections

### Overview 

CloudBeaver server may have a set of pre-configured database connections. 
This configuration is stored on server and cannot be changed by end-users.

End-user may choose one of pre-configured connection in the main CloudBeaver toolbar. Then user have to provide username/password in order to connect to such pre-configured datasource. No other parameters are needed.

See [[Server configuration|Server-configuration]] for information about server and workspace configuration.

### Datasources configuration file

All project-level configuration is stored in folder `${CLOUDBEAVER_WORKSPACE}/GlobalConfiguration/.dbeaver`.
Datasources are configured in file `data-sources.json`.

It has the same format as [DBeaver](https://github.com/dbeaver/dbeaver) datasources configuration file.
In version 1.0 CloudBeaver doesn't support UI for datasources configuration (mostly because it is quite complicated).

You can create this configuration in DBeaver and then copy to your server configuration folder. Then you can patch configuration manually by editing configuration json.