
# Azure Active Directory Configuration
## Create and configure application in Azure Active Directory
### Register application in Azure Active Directory 
Register a new application according to the [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#register-an-application).  
### Configure application credentials
Сloudbeaver uses the OpenId protocol for authorization in Azure Active Directory.  
For this it's necessary configure application secrets - more information on how to do this can be found in the [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).  
Do not forget to record the value of the secret key, it can only be obtained once, otherwise delete the existing secrets and go through this step again.

# Cloudbeaver Configuration
## Enabling Azure AD authentication provider
Go to the Administration menu and enable **Azure AD** in the Server configuration tab.

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_switcher.png)

## Configuring Azure AD identity provider
### Go to the Identity Providers tab and create a new configuration using the Azure AD details.
![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_provider.png)
### Add details from your Azure AD application into the new configuration in CloudBeaver

1. Open the application page [registered in the first step](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication/_edit#register-application-in-azure-active-directory) and copy the **Application (client) ID** value into the Cloudbeaver Azure AD provider **Application (client) ID** field.

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_application_page_app_id.png)

2. Open Azure Active Directory/Your Directory/Overiview page and  copy the **Tenant ID** or **Primary domain** (these values are equivalent) value into the Cloudbeaver Azure AD provider **Tenant ID** field.

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_application_page_tenant_id.png)

3. Copy the value ofsecret key [created in this step](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication/_edit#configure-application-credentials) into the **Secret Key** field.

4. Save Cloudbeaver configuration

# Configure Redirect link
1. Open **Azure AD provider configuration** in the Cloudbeaver and copy **Redirect ** link

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_redirect_link.png)

2. Add a redirect link to the Azure AD application (select **Web** as platform) - [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-a-redirect-uri)

# Testing Azure AD authentication
The new Federated tab becomes available after creating the configuration in the CloudBeaver authentication dialog. The user can select the configuration and thereafter login into the application using SSO.
![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_login_dialog.png)


# Optional configuration

Cloudbeaver supports the ability to read and display information about the user's first and last name from the OpeID token, so if you want to support this feature you need to add the **family_name** and **given_name** fields to the response token, more information on how to do this can be found in the [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-optional-claims#configuring-optional-claims) 

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_token_configuration.png)

