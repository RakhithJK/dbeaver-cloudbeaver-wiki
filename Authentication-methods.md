CloudBeaver offers several authentication methods. The administrator can set them when configuring CloudBeaver for the first time. Or it can be done later in the Administration Menu.

## CloudBeaver CE

![server_config_ce](https://user-images.githubusercontent.com/51405061/140599758-3e2371df-70c4-4f95-83d8-9b2bc2b91e88.png)

### Anonymous access
Users can work with CloudBeaver without authorization. Connections become available for anonymous access when the administrator:
1. creates connections in the Connection Management Menu and gives access to them for the User role (you can find more information for the roles at [Role management](https://github.com/dbeaver/cloudbeaver/wiki/Role-management) article). 

2. enables the Custom connections option in the Administration Menu. In this case connections can be configured on the main page by anonymous users and disappear after the session expirations.


### Local access
It is the local name/password based authentication. The administrator has to create users in the Administration and grant them a role which will define users’ permissions (more information about users can be found at [Users](https://github.com/dbeaver/cloudbeaver/wiki/Users) article).

### Reverse proxy access
Authentication based on headers of the HTTP request (more information about this authentication method can be found at [Reverse proxy header authentication](https://github.com/dbeaver/cloudbeaver/wiki/Reverse-proxy-header-authentication) article).

## CloudBeaver EE
CloudBeaver Enterprise Edition also supports AWS IAM and SAML authentication methods.

![1](https://user-images.githubusercontent.com/51405061/141135303-a4890c26-7e21-4ed1-a568-c4cef7090324.png)

### AWS IAM access 
Amazon Web Services authentication allows users to authorize to CloudBeaver EE with IAM credentials. Once an IAM user is authorized to CloudBeaver instance, the appropriate user is created in the application with the User role by default (you can find more information about AWS IAM authentication at [AWS IAM](https://github.com/dbeaver/cloudbeaver/wiki/AWS-IAM) article).

_Note: Local and AWS accounts, used during the first configuration of CloudBeaver EE instance, become associated with the administrator who configured it. It means that the administrator can login to the application with the local and the IAM credentials and a new user will not be created after using these IAM credentials._

### SAML access
SSO (Single Sign-On) authentication can be used for access to CloudBeaver EE. Once an SSO user is authorized to CloudBeaver instance, the appropriate user is created in the application with the User role by default (you can find more information about SSO authentication at [Single Sign On](https://github.com/dbeaver/cloudbeaver/wiki/Single-Sign-On) article).

## CloudBeaver AWS
CloudBeaver Enterprise Edition for AWS supports AWS IAM and SAML authentication methods, but local and anonymous authentication are not available in it.

![2](https://user-images.githubusercontent.com/51405061/141135465-810ee95a-441a-431c-836e-f46f27dc8eb7.png)


