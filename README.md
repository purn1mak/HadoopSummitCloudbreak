# HadoopSummitCloudbreak
Crash Course for Cloudbreak for Data Works Summit 2018 San Jose.
- [Prerequisites](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/aws_prerequisites.md)
  - a. Before launching Cloudbreak on AWS, you must meet the [AWS prerequisites.](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/aws_prerequisites.md)
  - b. Before launching Cloudbreak on Azure, you must meet the [Azure prerequisites.](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/azure_prerequisites.md)

- [1. Log into the Cloudbreak application](#1-log-into-the-cloudbreak-application)
  - a.Confirm the security exception
  - b.Login page
  - c.Create Cloudbreak Credentials
- [2. Creating an HDP cluster on AWS](#2-create-an-HDP-cluster-on-aws)
  - a.Basic cluster options(#a-baisc-cluster-options)
  - b.Advanced cluster options(#b-advance-cluster-options)
      - Availability zone
      - Choose image catalog
      - Prewarmed and base images
      - Enable lifetime management
      - Tags
- [3. Accessing a cluster](#3-accessing-a-cluster)
  - a.Cloudbreak user accounts
  - b.Finding cluster information in the web UI
  - c.Cluster summary
  - d.Cluster information
  - e.Event history
  - f.Accessing cluster via SSH
  - g.Access Ambari
- [4. Managing and monitoring clusters](#4-managing-and-monitoring-clusters)
  - a.Resize a cluster
  - b.Synchronize a cluster
  - c.Stop a cluster
  - d.Restart a cluster
  - e.Terminate a cluster
  - f.Force terminate a cluster
  - g.View cluster history
  - h.History report content
- [5. Autoscaling](#5-autoscaling)
  - 1. Enable Auto Scaling
  - 2. Defining an Alert
  - 3. Create a Scaling Policy
  - 4. Configure Autoscaling Settings
- [6. Creating an HDF cluster on AWS](#6-creating-an-hdf-cluster-on-aws)
  - [a. General Configuration](#a-general-configuration)
  - [b. Hardware and Storage](#b-hardware-and-storage)
  - [c. Gateway Configuration](#c-gateway-configuration)
  - [d. Network](#d-network)
  - [e. security](#e-security)
---------------

# Cloudbreak launches clusters on the cloud in 3 easy steps:
  - 1. Pick a Blueprint: Cloudbreak uses [Ambari Blueprints](https://cwiki.apache.org/confluence/display/AMBARI/Blueprints)  to have declarative Hadoop cluster definition. Blueprints can be designed for specialized applications and workloads (such as Data Science or IoT Apps). Cloudbreak includes a few default Blueprints for common cluster configurations but you can always upload your own Blueprint to build the cluster just the way you like it.
  - 2. Choose a Cloud: Cloudbreak is configured to work with cloud infrastructure resources (such as servers, network setup and security options). Choose the cloud infrastructure you want to use for the cluster.
  - 3. Launch Cluster: In this step, Cloudbreak obtains the chosen cloud infrastructure platform, installs Apache Ambari and applies the desired Blueprint. The result: your cluster is launched and ready to go!

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/3EasySteps.png)

## 1. Log into the Cloudbreak application

#### a.Confirm the security exception
Access https://cloud.eng.hortonworks.com/ 
Click on Advance and then proceed to cloudbreak server.
  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AdvancedConnectionWarning.png)
  
#### b. login page
Cloudbreak login page. Credentials will be provided for these services by the instructor. 

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CB_login.png)

#### c.Create Cloudbreak Credentials
Before launching Cloudbreak on AWS, you must meet the [prerequisites.](aws_prerequisites.md)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Credentials_1.png)

Pick the cloud provider of your choice

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Credentials_2.png)

Get the Access Key and Secret Key from the Prerequisites section

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Credentials_3.png)


## 2. Create an HDP cluster on aws

### a. Basic Cluster Options
Click the Create Cluster button and the Create Cluster wizard is displayed.

By default, Basic view is displayed.

**Cluster Name**: Enter a name for your cluster. The name must be between 5 and 40 characters, must start with a letter, and must only include lowercase letters, numbers, and hyphens.

**Region**: Select the region in which you would like to launch your cluster.

**Cluster Type**: Choose one of default cluster configurations.

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/GeneralConfig27.png)

Go with default storage options

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/HWStorage27.png)

**Gateway Topology**   
When creating a cluster, Cloudbreak installs and configures a gateway, powered by Apache Knox, to protect access to the cluster resources: This gateway is installed on the same host as the Ambari server.  
By default, the gateway is deployed and Ambari is proxied through the gateway.  
The choice of cluster services to expose and proxy through the gateway depends on your blueprint.   

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Gateway.png)
  
Go with default Network setup

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Network27.png)


On the **Security page**, provide the following:  
**Cluster User**: This will be the user that you should use to log in to Ambari and other cluster UIs. By default, this is admin.  
**Cluster Password**: Password for the cluster user.  
**SSH public key**: Select the existing public SSH key or paste your key. The key will be placed on the cluster VMs so that you can use the matching private key to access the VMs via SSH. [You can get this from the prerequisites section](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/aws_prerequisites.md#ssh-key-pair)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Security27.png)

### b. Advance Cluster Options

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ClusterAdvanceOptions.png)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AdvPreWarmed.png)

## 3. Accessing a Cluster

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ClusterInfo.png)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ConnectionWarning.png)


## 4. Managing and Monitoring Clusters
- a.Resize a cluster
- b.Synchronize a cluster
- c.Stop a cluster
- d.Restart a cluster
- e.Terminate a cluster
- f.Force terminate a cluster
- g.View cluster history
- h.History report content

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ManageCluster2.png)


For additional details visit [Cloudbreak documentation](https://hortonworks.github.io/cloudbreak-documentation/latest/index.html)


## 5. Autoscaling
  - 1. Enable Auto Scaling
  - 2. Defining an Alert
  - 3. Create a Scaling Policy
  - 4. Configure Autoscaling Settings
  
##### 1. Enable Auto Scaling  
   ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/EnableAutoscaling.png)

##### 2. Defining an Alert: 
After you have enabled autoscaling, define a metric-based or time-based alert.
   ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Alert.png)

##### 3. Creating a Scaling Policy
1. In the Policy Configuration section, provide needed information:
2. Click + to save the alert
   ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/PolicyConfiguration.png)
   
##### 4. Configure Autoscaling Settings:
After enabling autoscaling, perform these steps to configure the auto scaling settings for your cluster.
  - 1. In the Cluster Scaling Configuration, provide the following information:
      - Cooldown time: After an auto scaling event occurs, the amount of time to wait before enforcing another scaling policy.	
      - Minimum Cluster Size:	The minimum size allowed for the cluster. Auto scaling policies cannot scale the cluster below or above this size.
      - Maximum Cluster Size:	The maximum size allowed for the cluster. Auto scaling policies cannot scale the cluster below or above this size.
  - 2. Click Save to save the changes.

   ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ScalingConfiguration.png)

##### 2 new Worker nodes are being requested at 21:33 as per the Time based Alert
   ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AutoScaledHistory_1.png)

##### 2 new Worker nodes are created.
   ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AutoScalesHistory_2.png)

Look in Azure Dashboard for the newly created nodes.
   ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AutoscaledNodesAzure.png)

## 6. Creating an HDF cluster on AWS
As of Cloudbreak 2.7, you can deploy Hortonworks Data Flow (HDF) clusters.  Currently there are two HDF cluster types supported: Flow Management (NiFi) and <insert other type>.  We will walk you through deploying an HDF 3.1 Flow Management cluster using Cloudbreak 2.7.

In the left manu, click on `Clusters`.  Cloudbreak will display configured clusters.  Click the `CREATE CLUSTER` button.  Cloudbreak will display the Create Cluster wizard

#### a. General Configuration

By default, the General Configuration screen is displayed using the `BASIC` view.  The `ADVANCED` view gives you more control of AWS and cluster settings, to include tags.  You can change your view to `ADVANCED` manually or you can change your Cloudbreak preferences to show `ADVANCED` view by default.  We wil use the `BASIC` view.

   ![Image](https://github.com/jaraxal/HadoopSummitCloudbreak/blob/master/hdf-general-configuration.png)

**Credential**: Select the AWS credential you created.  Most users will only have 1 credential per platform which will be selected automatically.

**Cluster Name**: Enter a name for your cluster. The name must be between 5 and 40 characters, must start with a letter, and must only include lowercase letters, numbers, and hyphens.

**Region**: Select the region in w`hich you would like to launch your cluster.

**Platform Version**: Cloudbreak currently defaults to HDP 2.6.  Select the dropdown arrow and select `HDF 3.1`.

**Cluster Type**: As mentioned previously, there are two supported cluster types.  We'll select the `Flow Management` clsuter type.  This will allow us to deploy a an HDF/NiFi cluster.

Click the green `NEXT` button.

#### b. Hardware and Storage

Cloudbreak will display the `Hardware and Storage`screen.  On this screen, you have the ability to change the instance types, attached storage and where the Ambari server will be installed.  As you you can see, we will deploy 1 NiFi and 1 Zookeeper node.  In a prodution environment you would typically have at least 3 Zookeper nodes.  We will use the defaults.

   ![Image](https://github.com/jaraxal/HadoopSummitCloudbreak/blob/master/hdf-hardware.png)

Click the green `NEXT` button.

#### c. Gateway ConfigurationA

Cloudbreak will display the `Gateway Configuration` screen.  On this screen, you have the ability to enable a protected gateway.  This gateway uses Knox to provide a secure access point for the cluster.  Cloudbreak does not currently support configuring Knox for HDF.  We will leave this option disabled.

   ![Image](https://github.com/jaraxal/HadoopSummitCloudbreak/blob/master/hdf-gateway.png)

Click the green `NEXT` button.

#### d. Network

Cloudbreak will display the `Network` screen.  On this screen, you have the ability to specify the `Network`, `Subnet`, and `Security Groups`.  Cloudbreak defaults to creating new items.  For production use cases, we highly recommend creating and refining your own definitions within the cloud platform.  You can tell Cloudbreak to use those via the drop down menus.  We will use the default options to create new.

   ![Image](https://github.com/jaraxal/HadoopSummitCloudbreak/blob/master/hdf-network-1.png)

Click the green `NEXT` button.

#### e. Security

Cloudbreak will display the `Security` screen.  On this screen, you have the ability to specify the Ambari admin username and password.  You can create a new SSH key or selecting an existing on.  And finally, you have the ability to enable Kerberos on the cluster.  We will use `admin` for the username and `BadPass#1` for the password.  Select an existing SSH key from the drop down list.  We will NOT be enabling Kerberos.

   ![Image](https://github.com/jaraxal/HadoopSummitCloudbreak/blob/master/hdf-security.png)

Click the green `NEXT` button.