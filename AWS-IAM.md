## AWS Authentication

CloudBeaver Enterprise for AWS requires AWS IAM authentication to work with databases.  
You must enter a valid Access Key and Secret Key in order to login.  

CloudBeaver Enterprise for AWS does not keep your access/secret keys on the server-side. They are not saved in a database or in configuration files.  
Once your session expires, you will need to authenticate again. Authentication is always performed through remote AWS services.  

## Server configuration

When you open CloudBeaver EE in AWS for the first time you must enter your access/secret keys.  
The AWS user who configures CloudBeaver will become an administrator in this CloudBeaver EE instance (this user will have administrator permissions).  

After the server configuration finishes the current AWS account (the account to which administrator belongs), it will be associated with this CloudBeaver EE instance. Only AWS users from this account can authenticate in this CloudBeaver EE instance.  

You cannot create new users in CloudBeaver EE for AWS as it only works with real AWS users.  
The Administrator may grant different roles (including Administrator role) to the other AWS users in this account after they authenticate in this CloudBeaver instance.  

## IAM permissions

CloudBeaver EE uses the following AWS services in order to operate with databases (most of them are optional):

- STS (required): used for user authentication
- RDS: list RDS/Aurora instances for cloud databases explorer (describeDBInstances)
- Redshift: list Redshift clusters for cloud databases explorer (describeClusters)
- DynamoDB: all DynamoDB services for DynamoDB operating. Can be read-only for read-only DynamoDB access.
- DocumentDB: list DocumentDB clusters for cloud databases explorer (describeDBClusters)
- IAM (optional): additional user/organization information read (like account organization name)

CloudBeaver EE uses native database clients to connect and operate with most databases. It uses AWS services only to find  database instances and configure database connection.  
The only exception is the DynamoDB service which is a database driver by itself. You can limit DynamoDB access directly in the AWS console.

## Database authentication

As most AWS databases have their own authorization system (excluding DynamoDB) each database may require additional authentication parameters.  
It is usually a username/password pair.  
If you use IAM authentication for RDS/Aurora databases, then only the database username may be required and you can leave the password field empty.
