## AWS Authentication

CloudBeaver for AWS requires AWS IAM authentication to work with databases.  
You must enter valid Access Key and Secret Key in order to login.  

CloudBeaver doesn't keep your access/secret keys on the server-side. They are not saved in a database or in configuration files.  
Once your session will expire you will need to authenticate again. Authentication always performed thru remote AWS service.

## Server configuration

When you open CloudBeaver for the first time you must enter your access/secret keys. 
AWS user who configures CloudBeaver will become an administrator in CloudBeaver (it will have administrator permissions).  


## Database authentication