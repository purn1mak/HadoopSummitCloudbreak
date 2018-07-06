# Launching Cloudbreak on GCP
Before launching Cloudbreak on GCP, you must meet the following prerequisites.

## Meet the Prerequisites
Before launching Cloudbreak on GCP, you must meet the following prerequisites.

 - [GCP Account](#gcp-account)
 - [Service Account](#service-account)
 - [SSH Key Pair](#ssh-key-pair)
 - [Region and zone](#regional-and-zone)

### GCP account
In order to launch Cloudbreak on GCP, you must log in to your GCP account. If you don't have an account, you can create one at https://console.cloud.google.com. 
Once you log in to your GCP account, you must either create a project or use an existing project.

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CreateProject.png)

To create a new project, provide name, choose organization or leave it as No Organization.

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/NewProject.png)

Now Select this newly created Project.

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/SelectProject.png)

On the main dashboard page, you will find the Project ID. You will need this to define your credential in Cloudbbreak in a later step

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ProjectId.png)

  
### GCP - APIs Dashboard
Go to the Service Accounts screen by (1) clicking the menu in the top left, (2) hovering over APIs and Services, and (3) Clicking on Dashboard.  

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/APIsMenu.png)
 
### GCP - APIs & Services Dashboard
Verify that the Google Compute Engine API is listed and enabled. If it is not click on the Enable APIs button to search for and enable it.

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/APIServicesEnable.png)  

### Service account
Go to the Service Accounts screen by (1) clicking the menu in the top left, (2) hovering over IAM & Admin, and (3) Clicking on Service Accounts.

### Create Service Account - Step 1
Click "Create Service Account"

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CreateServiceAccount.png)  

### Create Service Account - Step 2
Give the service account a name
Check the "Furnish a new key" box. This will download a key to your computer when you finish creating the account.
If you are using Cloudbreak 2.7 or later, select JSON format key. Google has deprecated the P12 format and it will eventually be unsupported. 
If you are using Cloudbreak before 2.7, I strongly recommend that you move to 2.7 because of the many excellent new features and use JSON. In Cloudbreak 2.4, P12 is the only format that is supported.
Click the "Select a Role" dropdown
Select the required Compute Engine roles.
Select the Storage Admin role under Storage.
Click outside of the roles selection dropdown to reveal the "create" button.
All five of the roles shown are required for the service account

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CreateServiceStep2.png)  

### SSH key pair
Generate a new SSH key pair or use an existing SSH key pair. You will be required to provide it when launching the VM.
On Linux or macOS workstations, you can generate a key with the ssh-keygen tool.

Open a terminal on your workstation and use the ssh-keygen command to generate a new key. This command generates a private SSH key file and a matching public SSH key with the following structure:
where:

  [KEY_VALUE] is the key value that you generated.
  [USERNAME] is the user that this key applies to.

`ssh-rsa [KEY_VALUE] [USERNAME]`

### Editing public SSH key metadata
Add or remove project-wide public SSH keys from the [GCP Console:](https://console.cloud.google.com)

In the Google Cloud Platform Console, go to the metadata page for your project.
GO TO THE METADATA PAGE - Click on 1. Burger Menu 2. Compute Engine 3. Metadata 4. SSH Keys tab 

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Metadata.png)  

click Edit, Add Item and then Save.  

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/MetadataSSHKey.png)   


Modify the project-wide public SSH keys:

To add a public SSH key, click Add item at the bottom of the page. This will produce a text box. Copy the contents of your public SSH key file and paste them in to the text box. Repeat this process for each public SSH key that you want to add.
To remove a public SSH key, click the removal button next to it:

### Region and zone
Decide in which region and zone you would like to launch Cloudbreak. You can launch Cloudbreak and provision your clusters in all regions supported by GCP.
Clusters created via Cloudbreak can be in the same or different region as Cloudbreak; when you launch a cluster, you select the region in which to launch it.
