## Connection types in CB

### Pre-configured connections
Configuration is located in `${WORKSPACE}/GlobalConfiguration/.dbeaver/data-sources.json`.  
Preconfigured connections are always visible in the database navigator. Users can't delete or change them.  
Only administrator can edit them.  

### Template connections

Template connections are similar to provided connections, main difference is that they are not present in the database navigator by default.  
Users can add them to the navigator tree using main toolbar Connection->New Connection->From template. 
Only administrator can edit template connections.  

### Custom connections

Custom connections can be created by users (Note: configuration parameter `supportsCustomConnections` must be turned on).  
- Click on main toolbar->Connection->New Connection->Custom.
- Choose connection driver
- Fill connection parameters
- Click "Create" and connection will be added in the navigator tree

### Cloud connections

Cloud connections cannot be created or deleted by users explicitly. Their configuration is provided by cloud service provider (e.g. thru AWS API).
Once CB will find such connections (by using cloud configuration specified by server administrator) they will become visible in the navigator tree.
