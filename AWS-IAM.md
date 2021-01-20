## AWS Authentication

CloudBeaver Enterprise for AWS requires AWS IAM authentication to work with databases.  
You must enter valid Access Key and Secret Key in order to login.  

CloudBeaver Enterprise for AWS doesn't keep your access/secret keys on the server-side. They are not saved in a database or in configuration files.  
Once your session will expire you will need to authenticate again. Authentication always performed thru remote AWS services.  

## Server configuration

When you open CloudBeaver EE in AWS for the first time you must enter your access/secret keys.  
AWS user who configures CloudBeaver will become an administrator in this CloudBeaver instance (this user will have administrator permissions).  

After server configuration finish current AWS account (the account to which administrator belongs) will be associated with this CloudBeaver instance. Only AWS users from this account can authenticate in this CloudBeaver instance.  

You cannot create new users in CloudBeaver EE for AWS as it works only with real AWS users.  
Administrator may grant different roles (including Administrator role) to the another AWS users in this account after they will authenticate in this CloudBeaver instance.  

## IAM permissions

CloudBeaver EE uses following AWS services in order to operate with databases (most of them are optional):

- STS (required): used for user authentication
- RDS: list RDS/Aurora instances for cloud databases explorer (describeDBInstances)
- Redshift: list Redshift clusters for cloud databases explorer (describeClusters)
- DynamoDB: all DynamoDB services for DynamoDB operating. Can be read-only for read-only DynamoDB access.
- DocumentDB: list DocumentDB clusters for cloud databases explorer (describeDBClusters)
- IAM (optional): additional user/organization information read (like account organization name)

CloudBeaver EE uses native database clients to connect and operate with most databases. It uses AWS services only to find  database instances and configure database connection.  
The only exception is DynamoDB service which is a database driver by itself. You can limit DynamoDB access directly in AWS console.

## Database authentication

As most AWS databases have their own authorization system (excluding DynamoDB) each database may require additional authentication parameters.  
Usually it is a username/password pair.  
If you use IAM authentication for RDS/Aurora databases then only database username may be required and you can leave password field empty.
