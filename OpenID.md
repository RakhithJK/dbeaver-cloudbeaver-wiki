# OpenID configuration

### Enabling OpenID authentication
Go to the Administration menu and enable **OpenID** in the Server configuration tab.

![server_configuration_saml_switcher](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/server_configuration/server_configuration_saml_switcher.png)

### Configuring external identity provider

1. Go to the Identity Providers tab and create a new configuration using the OpenID details.

![openid_details](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/openid_details.png)

2. Add details from your OpenId into the new configuration in CloudBeaver. 

| Configuration in OpenID Provider | Configuration in CloudBeaver |
|-------------------------|------------------------------|
| [depends on provider]                        | Client ID                    |
| [depends on provider]                        | Client Secret                |
| [depends on provider]                        | IDP auth endpoint URL        |
| [depends on provider]                        | IDP token endpoint URL       |

See Azure AD configuration as an example of OpenID provider  

**Testing OpenID authentication**

The new Federated tab becomes available after creating the configuration in the CloudBeaver authentication dialog. The user can select the configuration and thereafter login into the application using SSO.

![openid_auth_dialog](https://github.com/dbeaver/cloudbeaver/wiki/images/authentication/openid_auth_dialog.png)