# Launching Cloudbreak on AWS
Before launching Cloudbreak on AWS, review and meet the prerequisites.

## Meet the Prerequisites
Before launching Cloudbreak on AWS, you must meet the following prerequisites.

 - [AWS Account](#aws-account)
 - [AWS Region](#aws-region)
 - [SSH Key Pair](#ssh-key-pair)
 - [Authentication](#authentication)
  [- 1. Key-based](#1-key-based)
  [- 2. Role-based](#2-role-based)
  
 ### AWS Account
 In order to launch Cloudbreak on AWS, you must log in to your AWS account. If you don't have an account, you can create one at https://aws.amazon.com/.
 ### AWS Region
 Decide in which AWS region you would like to launch Cloudbreak. The following AWS regions are supported:
![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Regions.png)
 ### SSH Key Pair
 Import an existing key pair or generate a new key pair in the AWS region which you are planning to use for launching Cloudbreak and clusters. You can do this using the following steps.

Steps
Navigate to the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
Check the region listed in the top right corner to make sure that you are in the correct region.
In the left pane, find NETWORK AND SECURITY and click Key Pairs.
Do one of the following:
Click Create Key Pair to create a new key pair. Your private key file will be automatically downloaded onto your computer. Make sure to save it in a secure location. You will need it to SSH to the cluster nodes. You may want to change access settings for the file using chmod 400 my-key-pair.pem.
Click Import Key Pair to upload an existing public key and then select it and click Import. Make sure that you have access to its corresponding private key.
You need this SSH key pair to SSH to the Cloudbreak instance and start Cloudbreak.

 ### Authentication
  
### 1. Key-based
If you are using key-based authentication for Cloudbreak on AWS, you must be able to provide your AWS access key and secret key pair. Cloudbreak will use these keys to launch the resources. You must provide the access and secret keys later in the Cloudbreak web UI later when creating a credential.

If you choose this option, all you need to do at this point is check your AWS account and make sure that you can access this key pair. You can generate new access and secret keys from the IAM Console > Users. Next, select a user and click on the Security credentials tab:

![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AWS_Users.png)
![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CreateAccessKey.png)
  
If you choose this option, you can proceed to Launch the VM.  
