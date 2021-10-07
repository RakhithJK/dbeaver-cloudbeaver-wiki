CloudBeaver Enterprise supports Federated Authentication for SSO (Single Sign-On) access into the application. Your provider must support SAML to access the application.

### SSO authentication set up

1. Go to the Administration menu and enable SAML in the Server configuration tab.
2. Go to the Identity Providers tab and create a new configuration using the SAML IdP (Identity Provider) details.
3. Open the created configuration and download the metadata file.
4. Go to the SAML IdP website and add the metadata parameters from the file (entityID and Location) to the SSO access settings, assign users and add the attribute mappings according to the SAML IdP requirements. 

The new SAML tab becomes available after creating the configuration in the CloudBeaver authentication dialogue with the list of configurations. A user can select a configuration and login for the application using SSO.

CloudBeaver Enterprise does not keep your authentication information on the server-side and in configuration files.
Once your session expires, you will need to authenticate again. When a user logs out from the application, CloudBeaver also performs a session logout from SAML IdP.

#### To set up SSO authentication for AWS
1. Go to the Administration menu and enable SAML in the Server configuration tab.
2. Go to the Identity Providers tab and create a new configuration using the SAML IdP (Identity Provider) details.
3. Open the created configuration and download the metadata file.
4. Go to the SAML IdP website and add the metadata parameters from the file (entityID and Location) to the SSO access settings, assign users and add the attribute mappings according to the SAML IdP requirements. [More information you can find here](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_create_saml_assertions.html).
5. Go to the AWS Settings tab and enable the Federated authentication.
6. Add the Proxy User. You can set the current user or add a new one. 

When an AWS user is logged into CloudBeaver using SSO, he has [the Proxy User and the IAM user's identity-based permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_getfederationtoken.html). The AWS User cannot receive further permission from the Proxy User than he already has based on the IAM user's identity-based permissions.

