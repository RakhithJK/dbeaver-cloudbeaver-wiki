# Table of contents: 
1. [Overview](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication/#overview)
2. [Enabling Azure AD authentication provider](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication/#enabling-azure-ad-authentication-provider)
3. [Azure Active Directory Configuration](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication/#azure-active-directory-configuration)
4. [Cloudbeaver Configuration](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication/#cloudbeaver-configuration)
5. [Testing](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication/#testing-azure-ad-authentication)


# Overview
CloudBeaver supports authorization through Azure AD.  
To do this, you must have:

* An active Azure account.
* Configured application in Azure AD.  
  You will need the following settings for your application from CloudBeaver:

  Name|Description
  ---|---
  Redirect Url | Url to which Azure AD will send a response about the authorization attempt request which is taken from the identity provider in CloudBeaver.

* Configured **Azure AD** identity provider in CloudBeaver.  
  You will need the following settings:

  Name|Description
  ---|---
  Domain / Tenant ID | Organization's domain or Tenant ID in Azure
  Application (client) ID | ID of Azure AD application
  Secret Key | Secret key from Azure AD application

# Enabling Azure AD authentication provider

This step is required for users to be able to use authorization through Azure AD, but immediately after that it will
not work, since you need to configure the provider.

1. Log into CloudBeaver as an administrator
2. Go to the Administration menu and enable **Azure AD** in the Server configuration tab.

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_switcher.png)

# Azure Active Directory Configuration

Authorization to the Microsoft platform is only possible using registered applications,
so we need to create an application in the Azure AD, if it does not exist, and configure it.

1. Register a new application in Azure AD according to
   the [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#register-an-application).
2. Сloudbeaver uses the OpenId protocol for authorization in Azure Active Directory.  
   For this it's necessary configure application secrets - more information on how to do this can be found in
   the [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).  
   Do not forget to record the value of the secret key, it can only be obtained once, otherwise delete the existing
   secrets and go through this step again.

### Optional configuration

Cloudbeaver supports the ability to read and display information about the user's first and last name from the OpenID
token, so if you want to support this feature you need to add the **family_name** and **given_name** fields to the
response token, more information on how to do this can be found in
the [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-optional-claims#configuring-optional-claims)

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_token_configuration.png)

# Cloudbeaver Configuration

## Create Identity Provider

To allow users to choose Azure AD as authorization method, a new identity provider must be created:

1. Go to the Identity Providers tab and create a new configuration using the Azure AD details.

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_provider.png)

## Configure Identity Provider

1. Set **Domain / Tenant ID**  
   Open Azure Active Directory/Your Directory/Overiview page and copy the **Tenant ID** or **Primary domain** (these
   values are equivalent) value into the Cloudbeaver Azure AD provider **Tenant ID** field.
   How to get **Tenant ID** value in other ways you can
   read [here](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_application_page_tenant_id.png)

2. Set **Application (client) ID**  
   Open the application page [registered in this step point 1](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication#azure-active-directory-configuration) and copy the value into the Cloudbeaver Azure AD provider **Application (client) ID**
   field.

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_application_page_app_id.png)

3. Set **Secret Key**  
   Copy the value of secret
   key [created in this step point 2](https://github.com/dbeaver/cloudbeaver/wiki/Azure-AD-authentication#azure-active-directory-configuration)
   into the **Secret Key** field.

4. Save identity Provider configuration

## Configure Redirect link
1. Open **Azure AD provider configuration** in the Cloudbeaver and copy **Redirect** link

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_redirect_link.png)

2. Add a redirect link to the Azure AD application (select **Web** as platform) - [official Microsoft documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-a-redirect-uri)

# Testing Azure AD authentication
The new Federated tab becomes available after creating the configuration in the CloudBeaver authentication dialog. The user can select the configuration and thereafter login into the application using SSO.

![](https://github.com/dbeaver/cloudbeaver/wiki/images/administration/identify_providers/aad/aad_login_dialog.png)

