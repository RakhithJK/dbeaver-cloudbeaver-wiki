# Authentication methods overview

CloudBeaver offers several authentication methods. The administrator can set them when configures CloudBeaver for the first time or in the Administration menu later.

## CloudBeaver CE

![server_config_ce](https://user-images.githubusercontent.com/51405061/140599758-3e2371df-70c4-4f95-83d8-9b2bc2b91e88.png)

### Anonymous access
Users can work with CloudBeaver without authorization. Connections become available for anonymous access when the administrator:
1. creates connections in the Connection management menu and gives access to them for the User role (more information about roles you can find in [Role management](https://github.com/dbeaver/cloudbeaver/wiki/Role-management) article). 

2. enables the Custom connections option in the Administration. In this case connections can be configured on the main page by anonymous users and disappear after the session expiration.


### Local access
It is the local name/password based authentication. The administrator has to create users in the Administration and grant them a role which will define users’ permissions (more information about users you can find in [Users](https://github.com/dbeaver/cloudbeaver/wiki/Users) article).

## CloudBeaver EE
CloudBeaver Enterprise Edition also supports AWS and SAML authentication methods.

![server_config_ee](https://user-images.githubusercontent.com/51405061/140599861-91a45b4f-cb73-4c76-9d17-f98eecbd1382.png)

### AWS access 
Amazon Web Services authentication allows users to authorize to CloudBeaver EE with IAM credentials. Once an IAM user is authorized to CloudBeaver instance, the appropriate user is created in the application with the User role by default (more information about AWS IAM authentication you can find in [AWS IAM](https://github.com/dbeaver/cloudbeaver/wiki/AWS-IAM) article).

_Note: Local and AWS accounts, used during the first configuration of CloudBeaver EE instance, become associated with the administrator who configured it. It means that the administrator can login to the application with the local and the IAM credentials and a new user will not be created after using these IAM credentials._

### SAML access
SSO (Single Sign-On) authentication can be used for access to CloudBeaver EE. Once an SSO user is authorized to CloudBeaver instance, the appropriate user is created in the application with the User role by default (more information about SSO authentication you can find in [Single Sign On](https://github.com/dbeaver/cloudbeaver/wiki/Single-Sign-On) article).

## CloudBeaver AWS
CloudBeaver Enterprise Edition for AWS supports AWS and SAML authentication methods, but local and anonymous authentication aren’t available in it.

![server_config_aws](https://user-images.githubusercontent.com/51405061/140599904-15d1d0ee-c732-40df-82a2-4042309f3d1f.png)


