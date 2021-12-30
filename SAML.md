# SAML configuration

If your Identity Provider uses SAML (Security Assertion Markup Language), follow this guide.

### Enabling SAML authentication

Go to the Administration menu and enable **SAML** in the Server configuration tab.

[[https://github.com/dbeaver/cloudbeaver/wiki/images/administration/server_configuration/server_configuration_saml_switcher.png]]

### Configuring an external identity provider

1.  Go to the Identity Providers tab and create a new configuration using the SAML IdP details.

[[https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/identify_providers_saml_configuration_creation.png]]

2.  Add details from your SAML IdP into the new configuration in CloudBeaver.

### Configuring CloudBeaver integration in an external identity provider

1.  Open the created configuration in CloudBeaver and download the metadata file.

[[https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/identify_providers_saml_configuration_metadata_file.png]]

2.  Go to the SAML IdP website and add the metadata parameters from the file (entityID and Location) to the SSO access settings, assign users and add the attribute mappings according to the SAML IdP requirements.

**Each identity provider has its own configuration procedure, we will show how to do it in AWS in the next chapter**.

### AWS SSO configuration

**Configuration**

1.  Go to the Identity Providers tab and create a new configuration using the SAML IdP details as it is described above.

2.  Add details from your SAML IdP into the new configuration in CloudBeaver. 

| Configuration in Amazon | Configuration in CloudBeaver |
|-------------------------|------------------------------|
| AWS SSO sign-in URL     | IDP signon URL               |
| AWS SSO sign-out URL    | IDP logout URL               |
| AWS SSO issuer URL      | IDP Entity ID                |

3.  You can upload the metadata file to fill parameters automatically. 

4.  Or you can specify parameters manually:

| Parameter                 | Value                                           |
|---------------------------|-------------------------------------------------|
| Application ACS URL       | `https://HOST_NAME/api/saml/CONFIG_ID/acs`      |
| Application SAML audience | `https://HOST_NAME/api/saml/CONFIG_ID/metadata` |

Where HOST_NAME is the host name of your CloudBeaver installation, CONFIG_ID is the identifier of your SAML configuration.

**Attributes**

Attributes explanation:

| Attribute                                              | Value           | Meaning                                                             |
|--------------------------------------------------------|-----------------|---------------------------------------------------------------------|
| Subject                                                | ${user:email}   | User unique identifier (nameId). It is usually an email address.    |
| https://aws.amazon.com/SAML/Attributes/SessionDuration | 1800            | Session duration in seconds. 1800 (30 minutes) is the default value |
| https://aws.amazon.com/SAML/Attributes/Role            | roleARN, idpARN | IAM role identifier                                                 |

Role is the most important attribute, it defines which IAM role will be used for user federation session. Role format: roleARN, idpARN. You can get role ARN in AWS IAM section <https://console.aws.amazon.com/iamv2/home#/roles>. Role ARN looks like this: _arn:aws:iam::123678087624:role/RoleForSAMLAccess_.

You can get IDP ARN in AWS identity providers page <https://console.aws.amazon.com/iamv2/home#/identity_providers>. IDP ARN looks like this: _arn:aws:iam::123678087624:saml-provider/GSuiteSAML_.

### Testing SAML authentication

The Federated tab becomes available in the CloudBeaver authentication dialog after creating the configuration. The user can select the configuration and thereafter login into the application using SSO.

[[https://github.com/dbeaver/cloudbeaver/wiki/images/authetication_dialog_federated_saml.png]]