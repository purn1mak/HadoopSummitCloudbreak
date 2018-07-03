# Launching Cloudbreak on GCP
Before launching Cloudbreak on GCP, you must meet the following prerequisites.

## Meet the Prerequisites
Before launching Cloudbreak on GCP, you must meet the following prerequisites.

 - [AWS Account](#aws-account)
 - [Service Account](#service-account)
 - [SSH Key Pair](#ssh-key-pair)
 - [Virtual network](#Key-Based-Authentication)
 - [Security group]
 - [Region and zone]

### GCP account
In order to launch Cloudbreak on GCP, you must log in to your GCP account. If you don't have an account, you can create one at https://console.cloud.google.com. 
Once you log in to your GCP account, you must either create a project or use an existing project.

  
### AWS Account
 In order to launch Cloudbreak on AWS, you must log in to your AWS account. If you don't have an account, you can create one at https://aws.amazon.com/.

### Service account

### SSH key pair
Generate a new SSH key pair or use an existing SSH key pair. You will be required to provide it when launching the VM.

### Virtual network
You must have a virtual network configured on your cloud provider.

### Security group
Ports 22 (SSH), 80 (HTTPS), and 443 (HTTPS) must be open on the security group

### Region and zone
Decide in which region and zone you would like to launch Cloudbreak. You can launch Cloudbreak and provision your clusters in all regions supported by GCP.
Clusters created via Cloudbreak can be in the same or different region as Cloudbreak; when you launch a cluster, you select the region in which to launch it.
