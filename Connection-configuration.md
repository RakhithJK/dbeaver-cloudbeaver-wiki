## Connection types in CB

1. Provided connections: configuration is located in `${WORKSPACE}/GlobalConfiguration/.dbeaver/provided-connections.json`.  
Provided connections are always visible in the database navigator. Users can't delete or change them.
1. Preconfigured connections: configuration is located in `${WORKSPACE}/GlobalConfiguration/.dbeaver/data-sources.json`.  
Preconfigured connections are similar to provided connections, main difference is that they are not present in the database navigator by default. Users can add them to the navigator tree using main toolbar Connection->New Connection->Preconfigured.