The Administrator can create users for local name/password based authentication in the Administration Menu.

## CloudBeaver CE

## Adding a New User in the Administration Menu

1. **Navigating to the Access Management Tab:** Within the Administration Menu, find and select the `Access Management` tab.
2. **Initiating the Creation of a New User:** To begin the process of creating a new user, click on the `Add` button located within the `Access Management` tab.
3. **Entering User Details:** Here, you will be required to input a username and password. These credentials will be used by the new user for logging into the system.
4. **Assigning a Team to the New User:** A team will define the permissions the user has within the system. For additional information regarding teams and their definitions, please refer to the [Team management](https://github.com/dbeaver/cloudbeaver/wiki/Role-management) article.
5. **Setting Connection Access:** If necessary, you can provide the user with connection access. This setting can be found and adjusted within the `Connection Access` tab.
6. **Finalizing User Creation:** To complete the process and create the new user, click on the `Create` button.



![Create User Dialog](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/access_management/create_user_dialog.png)
The newly created user can now be authenticated to CloudBeaver using local authentication. The user's permissions are defined according to their assigned profile.

## CloudBeaver EE
CloudBeaver Enterprise Edition also allows you to configure AWS and SSO users.

### AWS and Federated users
When a user is authorized to the CloudBeaver EE instance via AWS IAM or Federated authentication for the first time, a corresponding user is automatically created within the application, with the 'User' team assigned by default. Post-creation, the administrator can alter the user's team as needed.

It is important to note that administrators cannot create new AWS or Federated users directly within the application. The system is designed to work with existing, legitimate AWS and Federated users.

## CloudBeaver AWS
CloudBeaver AWS exclusively supports configuration for AWS and Federated users, as it does not provide local access. As a consequence, local users cannot be created within the Product environment.

> Remember, user management is an important aspect of maintaining system security. Always ensure that users are only granted access and permissions necessary for their tasks.