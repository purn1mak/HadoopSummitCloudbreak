# HadoopSummitCloudbreak
Crash Course for Cloudbreak for Data Works Summit 2018 San Jose.
- [1. Log into the Cloudbreak application](#log-into-the-cloudbreak-application)
  - a.Confirm the security exception
  - b.Login page
  - c.Create Cloudbreak Credentials
- [2. Creating a cluster on AWS](#create-a-cluster-on-aws)
  - a.Advanced cluster options
  - b.Availability zone
  - c.Choose image catalog
  - d.Prewarmed and base images
  - e.Enable lifetime management
  - f.Tags
  - g.Storage
  - h.Recipes
  - i.Management Packs
  - j.External sources
  - k.Ambari server master key
  - l.Enable Kerberos security
- [3. Accessing a cluster](#accessing-a-cluster)
  - a.Cloudbreak user accounts
  - b.Finding cluster information in the web UI
  - c.Cluster summary
  - d.Cluster information
  - e.Event history
  - f.Accessing cluster via SSH
  - g.Access Ambari
- [4.Managing and monitoring clusters](#4)
  - a.Resize a cluster
  - b.Synchronize a cluster
  - c.Stop a cluster
  - d.Restart a cluster
  - e.Terminate a cluster
  - f.Force terminate a cluster
  - g.View cluster history
  - h.History report content
  
---------------

# Cloudbreak launches clusters on the cloud in 3 easy steps:
  - 1. Pick a Blueprint: Cloudbreak uses [Ambari Blueprints](#https://cwiki.apache.org/confluence/display/AMBARI/Blueprints)  to have declarative Hadoop cluster definition. Blueprints can be designed for specialized applications and workloads (such as Data Science or IoT Apps). Cloudbreak includes a few default Blueprints for common cluster configurations but you can always upload your own Blueprint to build the cluster just the way you like it.
  - 2. Choose a Cloud: Cloudbreak is configured to work with cloud infrastructure resources (such as servers, network setup and security options). Choose the cloud infrastructure you want to use for the cluster.
  - 3. Launch Cluster: In this step, Cloudbreak obtains the chosen cloud infrastructure platform, installs Apache Ambari and applies the desired Blueprint. The result: your cluster is launched and ready to go!

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/3EasySteps.png)

## Log into the Cloudbreak application

#### a.Confirm the security exception
Access https://cloud.eng.hortonworks.com/ 
Click on Advance and then proceed to cloudbreak server.
  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/AdvancedConnectionWarning.png)
  
#### b. login page
Cloudbreak login page. Credentials will be provided for these services by the instructor. 

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CB_login.png)

#### c.Create Cloudbreak Credentials

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Credentials_1.png)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Credentials_2.png)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/Credentials_3.png)


## Create a cluster on aws

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CC_1.png)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CC_2.png)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CC_3.png)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/CC_4.png)


## Accessing a Cluster

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ClusterInfo.png)

  ![Image](https://github.com/purn1mak/HadoopSummitCloudbreak/blob/master/ConnectionWarning.png)
