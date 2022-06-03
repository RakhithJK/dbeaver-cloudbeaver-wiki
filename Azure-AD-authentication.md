
# Azure AD Configuration
## Create and configure application in Azure Active Directory
### Register application in Azure Active Directory 
Register a new application according to the [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#register-an-application).  
### Configure application credentials
Сloudbeaver uses the OpenId protocol for authorization in Azure Active Directory.  
For this it's necessary configure application secrets - more information on how to do this can be found in the [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).  
Do not forget to record the value of the secret key, it can only be obtained once, otherwise delete the existing secrets and go through this step again.

# Cloudbeaver Configuration
## Enabling Azure AD authentication
Go to the Administration menu and enable **Azure AD** in the Server configuration tab.

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_switcher.png)