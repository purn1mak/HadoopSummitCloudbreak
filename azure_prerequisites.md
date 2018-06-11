# Launching Cloudbreak cluster on Azure
Before launching Cloudbreak cluster on Azure, review and meet the prerequisites.

## Meet the Prerequisites
Before launching Cloudbreak on Azure, you must meet the following prerequisites.

 - [Azure Account](#azure-account)
 - [Azure Region](#azure-region)
 - [SSH Key Pair](#create-an-ssh-key-pair)
 - [Authentication](#authentication)
     - [1. Key-based](#1-key-based)
     - [2. Role-based](#2-role-based)
 - [Subscription Id](#For Subscription ID)
 - [Tenant ID](#For Tenant ID)
 - [Application ID](#For Application ID)

### Azure Account
In order to launch Cloudbreak on the Azure, log in to your existing Microsoft Azure account. If you don't have an account, you can set it up at https://azure.microsoft.com.

### Azure Region
Decide in which Azure region you would like to launch Cloudbreak. You can launch Cloudbreak and provision your clusters in all regions [supported by Microsoft Azure.](https://azure.microsoft.com/en-us/global-infrastructure/regions/)

### Create an SSH key pair
When launching Cloudbreak, you will be required to provide your public SSH key. If needed, you can generate a new SSH key pair:

  - On MacOS X and Linux using ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  - On Windows using PuTTygen
  - On Azure shell. Launch azure shell via a browser https://shell.azure.com/ and Create an SSH key pair
    Use the ssh-keygen command to generate SSH public and private key files that are by default created in the ~/.ssh directory.
    
![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/azure_key.png)


### Authentication


### For Subscription ID
1. Search for Subscription Service
2. Overview
3. Subscription ID

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AzureSubscriptionID.png)

### For Tenant ID
1. Look for Azure Active Directory
2. Properties
3. Directory ID is Tenant ID

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AzureTenantId.png)

### For Application ID
1. Look for Azure Active Directory
2. App registration
3. Identify the application for cloudbreak
4. Pick the Application Id associated

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ApplicationId.png)

### For App Key
1. Look for Azure Active Directory
2. App registration
3. Identify the application for cloudbreak
4. Keys
5. Generate new Key or access an existing Key. This key is visible the first time its created only, so please makes ure to save it in a safe place.

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AppKey.png)
