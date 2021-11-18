CloudBeaver Enterprise supports Federated Authentication for SSO (Single Sign-On) access into the application. Your provider must support SAML to access the application.

### SAML configuration

#### Enabling SAML authentication

Go to the Administration menu and enable SAML in the Server configuration tab.

![1](https://user-images.githubusercontent.com/51405061/138433150-8e7c23d1-36d7-427d-a7ad-47669a6f6c8b.png)

#### Configuring external identity provider

Go to the Identity Providers tab and create a new configuration using the SAML IdP (Identity Provider) details.

![chrome_Nmyjww6h0Q](https://user-images.githubusercontent.com/51405061/138426363-b245ce89-aaa9-4e99-9df9-de147ba27689.png)

#### Configuring CloudBeaver integration in external identity provider

Open the created configuration and download the metadata file.

![3](https://user-images.githubusercontent.com/51405061/138433162-816e08d2-cec3-4462-a1cd-4167e01562a2.png)

Go to the SAML IdP website and add the metadata parameters from the file (entityID and Location) to the SSO access settings, assign users and add the attribute mappings according to the SAML IdP requirements.  
Each identity provider has its own configuration procedure, we will show how to do it in AWS in the next chapter.  

#### AWS SSO configuration

![aws](https://user-images.githubusercontent.com/51405061/138433882-179771b6-71c3-4a79-9cab-7dcc7cf13f50.png)

#### Configuring AWS proxy account

In order to provide users permission to your AWS cloud resources (RDS, DynamoDB, etc) you need to configure AWS federated access proxy user.  

You can more information find here: [Configuring SAML assertions for the authentication response](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_create_saml_assertions.html).

Go to the AWS Settings tab and enable the Federated authentication.

![1-2](https://user-images.githubusercontent.com/51405061/138433651-46dba1e6-054b-42a9-b940-d65ec6eada90.png)

Add the Proxy User on the same page. You can set the current user or add a new one. 

When an AWS user is logged into CloudBeaver using SSO, it has [the Proxy User and the IAM user's identity-based permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_getfederationtoken.html). 
Actual permission set and user role are configured in attribute mappings of SAML integration.  

![attribute-mappings](images/aws/aws-attribute-mappings.png)

![explorer](images/aws-explorer.png)
XXX

Attributes explanation:

Attribute | Value | Meaning
---|---|---
Subject | ${user:email} | User unique identifier (nameId). It is usually an email address.
`https://aws.amazon.com/SAML/Attributes/SessionDuration` | 1800 | Session duration in seconds. 1800 (30 minutes) is the default value
`https://aws.amazon.com/SAML/Attributes/Role` | roleARN,idpARN | IAM role identifier

Role is the most important attribute, it defines which IAM role will be used for user federation session.
Role format: roleARN,idpARN  

You can get role ARN in AWS IAM section https://console.aws.amazon.com/iamv2/home#/roles . Role ARN looks like this: `arn:aws:iam::123678087624:role/RoleForSAMLAccess,
You can get IDP ARN in AWS identity providers page https://console.aws.amazon.com/iamv2/home#/identity_providers . IDP ARN looks like this: 
arn:aws:iam::123678087624:saml-provider/GSuiteSAML

#### Notes 

CloudBeaver does not keep your authentication information on the server-side and in configuration files.
Once your session expires, you will need to authenticate again. When a user logs out from the application, CloudBeaver also performs a session logout from SAML IdP.


### Testing SAML authentication

The new SAML tab becomes available after creating the configuration in the CloudBeaver authentication dialog. This is where the user can select the configuration and thereafter login into the application using SSO.

![chrome_enlTzZHaQh](https://user-images.githubusercontent.com/51405061/138428908-298910d9-0adc-4258-a59f-ac2e4b51514e.png)



