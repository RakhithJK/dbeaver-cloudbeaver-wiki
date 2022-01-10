## Overview 

It is possible to configure CloudBeaver to save database credentials (user names and passwords) in CloudBeaver storage.  
In this case, users won't need to enter database credentials every time they connect to a database.  

However, the most secure way is to disable this option.  See options "Save credentials" and "Save user credentials" in administrator console, page "Server configuration".

## Credentials storage

There are two types of database connections: global and user.  
Global connections are managed by CloudBeaver administrators, user connections are managed by users themselves.  

Global database configuration is stored in workspace sub-folder `GlobalConfiguration`/`.dbeaver`.  
Database configurations are stored in the file `data-sources.json`, database credentials are stored in the file `credentials-config.json`. File credentials-config.json is encrypted by a special key which is stored in CloudBeaver distribution.

User configuration are stored in workspace sub-folders `user-projects`/`USER_NAME`/`.dbeaver`.

Potentially, if an intruder/malware software will get access to CloudBeaver server filesystem then it will get access to all stored user credentials.