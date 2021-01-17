## AWS Authentication

"CloudBeaver for AWS" requires AWS IAM authentication to work with databases.  
You must enter valid Access Key and Secret Key in order to login.  

CloudBeaver doesn't keep your access/secret keys on the server-side. They are not saved in a database or in configuration files.  
Once your session will expire you will need to authenticate again. Authentication always performed thru remote AWS services.  

## Server configuration

When you open CloudBeaver for the first time you must enter your access/secret keys.  
AWS user who configures CloudBeaver will become an administrator in this CloudBeaver instance (it will have administrator permissions).  

After server configuration finish current AWS account (the account to which administrator belongs) will be associated with this CloudBeaver instance. Only AWS users from this account can authenticate in this CloudBeaver instance.  

You cannot create new users in "CloudBeaver for AWS" as it works only with real AWS users.  
Administrator may grant different roles (including Administrator role) to the another AWS users in this account after they will authenticate in this CloudBeaver instance.  

## Required IAM permissions

CloudBeaver uses following AWS services in order to operate with databases:

- STS (required)
- RDS
- Redshift
- DynamoDB
- DocumentDB

## Database authentication

Besides general AWS user authorization particular databases may require additional authentication.

- RDS
   - PostgreSQL
   - MySQL
- DocumentDB
