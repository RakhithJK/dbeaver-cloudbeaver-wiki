## Connection types in CB

### Pre-configured connections
The configuration is located in `${WORKSPACE}/GlobalConfiguration/.dbeaver/data-sources.json`.  
Preconfigured connections are always visible in the database navigator. Users cannot delete or change them.  
Only the administrator can edit them.  

### Template connections

Template connections are similar to the provided connections. The main difference is that they are not present in the database navigator by default.  
Users can add them to the navigator tree by using the main toolbar Connection->New Connection->From template. 
Only the administrator can edit the template connections.  

### Custom connections

Custom connections can be created by users (Note: configuration parameter `supportsCustomConnections` must be turned on).  
- Click on the main toolbar->Connection->New Connection->Custom.
- Choose the connection driver
- Fill in the connection parameters
- Click "Create" and the connection will be added in the navigator tree

### Cloud connections

Cloud connections cannot explicitly be created or deleted by users. Their configuration is provided by a cloud service provider (e.g. thru AWS API).
Once CB will find such connections (by using cloud configuration specified by the server administrator) they will become visible in the navigator tree.
