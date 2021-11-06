# Users
The Administrator can create users for local name/password based authentication in the Administration menu.

## CloudBeaver CE
### Local user creation


1. Go to the Users tab of the Administration menu and press the Add button.
1. Create the username and password.
1. Grant a role to the user. It will define the user’s permissions (more information about roles you can find in [Role management](https://github.com/dbeaver/cloudbeaver/wiki/Role-management) article).
1. Give a connection access to the user in the Connection access tab if it is necessary.
1. Press the Create button.

![Users](https://user-images.githubusercontent.com/51405061/140600070-3c906e71-197f-435b-927b-4e7f898896c1.png)
The created user can be authorized to CloudBeaver using local authentication and has permissions according to his profile.  

## CloudBeaver EE
CloudBeaver Enterprise Edition also allows to configure AWS and SSO users.

### AWS and SSO users
When a user is authorized to CloudBeaver EE instance with AWS or SAML authentication for the first time, the appropriate user is created in the application with the User role by default. The administrator can change the user’s role after that. 
The creation of new AWS and SSO users isn’t possible by the Administrator as it only works with real AWS and SSO users. 

## CloudBeaver AWS
CloudBeaver Enterprise Edition for AWS allows to configure only  AWS and SSO users, because it doesn’t have local access and local users cannot be created there.