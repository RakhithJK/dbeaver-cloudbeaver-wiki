CloudBeaver Enterprise supports Federated Authentication for SSO (Single Sign-On) access into the application. Your provider must support SAML for it.

### SSO authentication set up

1. Go to the Administration menu and enable SAML in the Server configuration tab.
2. Go to the Identity Providers tab and create a new configuration using SAML IdP (Identity Provider) details.
3. Open the created configuration and download the metadata file.
4. Go to SAML IdP website and add the metadata parameters from the file (entityID and Location) to SSO access settings, assign users and add attribute mappings according SAML IdP requerements. 

The new SAML tab becomes available after it in CloudBeaver authentication dialogue with the list of created configurations. A user can select a configuration and login to the application using SSO.

CloudBeaver Enterprise does not keep your authentication information on the server-side and in configuration files.
Once your session expires, you will need to authenticate again. When a user logs out from the application, CloudBeaver also performs session logout from SAML IdP.

#### To set up SSO authentication for AWS

1. Go to the Administration menu and enable SAML in the Server configuration tab.
2. Go to the Identity Providers tab and create a new configuration using SAML IdP (Identity Provider) details.
3. Open the created configuration and download the metadata file.
4. Go to SAML IdP website and add the metadata parameters from the file (entityID and Location) to SSO access settings, assign users and add attribute mappings according SAML IdP requerements. 
5. Go to the AWS Settings tab and enable Federated authentication.
6. Add the Proxy User. You can set the current user or add a new one. 

When an AWS user is logged into CloudBeaver using SSO, he has the Proxy User and the IAM user's identity-based permissions. The AWS User can't receive more permissions from the Proxy User than he already has based on the IAM user's identity-based permissions.