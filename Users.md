The Administrator can create users for local name/password based authentication in the Administration Menu.

## CloudBeaver CE
### Local user creation


1. Go to the Users tab of the Administration Menu and press the Add button.
1. Create a username and password.
1. Grant a role to the user. It will define the user’s permission (you can find more information about roles at [Role management](https://github.com/dbeaver/cloudbeaver/wiki/Role-management) article).
1. Give connection access to the user in the Connection Access tab if it is necessary.
1. Press the Create button.

![Users](https://user-images.githubusercontent.com/51405061/140600070-3c906e71-197f-435b-927b-4e7f898896c1.png)
The created user can be authorized to CloudBeaver using local authentication and has permission according to his profile.  

## CloudBeaver EE
CloudBeaver Enterprise Edition also allows you to configure AWS and SSO users.

### AWS and SSO users
When a user is authorized to CloudBeaver EE instance with AWS IAM or SAML authentication for the first time, the appropriate user is created in the application with the User role by default. The administrator can change the user’s role after that. 
The creation of new AWS and SSO users is not possible by the Administrator as it only works with real AWS and SSO users. 

## CloudBeaver AWS
CloudBeaver Enterprise Edition for AWS allows you to configure only  AWS and SSO users, because it does not have local access and local users cannot be created there.