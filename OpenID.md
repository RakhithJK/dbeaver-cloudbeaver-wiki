# OpenID configuration

### Enabling OpenID authentication
Go to the Administration menu and enable **OpenID** in the Server configuration tab.

[[https://github.com/dbeaver/cloudbeaver/wiki/images/administration/server_configuration/server_configuration_saml_switcher.png]]

### Configuring external identity provider

1. Go to the Identity Providers tab and create a new configuration using the OpenID details.

[[https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/openid_details.png]]

2. Add details from your OpenId into the new configuration in CloudBeaver. 

| Configuration in OpenID | Configuration in CloudBeaver |
|-------------------------|------------------------------|
|                         | Client ID                    |
|                         | Client Secret                |
|                         | IDP auth endpoint URL        |
|                         | IDP token endpoint URL       |

  

**Testing OpenID authentication**

The new Federated tab becomes available after creating the configuration in the CloudBeaver authentication dialog. The user can select the configuration and thereafter login into the application using SSO.

[[https://github.com/dbeaver/cloudbeaver/wiki/images/authentication/openid_auth_dialog.png]]