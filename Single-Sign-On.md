# Single Sign-On

CloudBeaver Enterprise supports federated authentication for Single Sign-On (SSO) access into the application. 

SSO is an authentication service which permits a user to log in with single credentials to multiple applications.

SSO in Cloudbeaver allows to:

-   log in to the application by users who have been given rights.

-   get access to databases according to users' roles.

Cloudbeaver supports SAML and OpenID  authentication methods for SSO.

## SSO for AWS 

You can configure SSO access for AWS. In order to provide users permission to your AWS cloud resources (RDS, DynamoDB, etc.) you need to configure AWS federated access proxy user. You can find more information here: [configuring SAML assertions for the authentication response](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_create_saml_assertions.html):

1.  Go to the AWS Settings tab and enable the Federated authentication. 

[[https://github.com/dbeaver/cloudbeaver/wiki/images/administration/aws_settings/administration_aws_settings.png]]

2.  Add the Proxy User on the same page. You can set the current user or add a new one.

3.  Create SAML configuration. You can find more information here: [[SAML Authentication|SAML]]

When an AWS user is logged into CloudBeaver using SSO, it has [the Proxy User and the IAM user's identity-based permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_getfederationtoken.html).

Actual permission set and user role are configured in attribute mappings of SAML integration.

### Notes: 

CloudBeaver does not keep your authentication information on the server-side and in configuration files.

Once your session expires, you will need to authenticate again. When a user logs out from the application, CloudBeaver also performs a session logout from Id Provider.