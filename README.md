# MongoDB Atlas Tutorial
This lab provides a quick tutorial and hands on experience on how to get started using MongoDB Atlas

# What is MongoDB Atlas?
Database-as-a-Service (DBaaS) is a service that allows you to set up, deploy, and scale a database without worrying about on-premise physical hardware, software updates, and the details of configuring for performance. With DBaaS, a cloud provider does all that for you—and gets you up and running right away.

[MongoDB Atlas](https://www.mongodb.com/cloud/atlas) is a fully-managed cloud database that handles all the complexity of deploying, managing, and healing your deployments on the cloud service provider of your choice (AWS , Azure, and GCP). MongoDB Atlas is the best way to deploy, run, and scale MongoDB in the cloud. With Atlas, you’ll have a MongoDB database running with just a few clicks, and in just a few minutes.

## MongoDB Atlas terminologies
### Organizations 
In the organizations and projects hierarchy, an organization can contain many projects. Under this structure, you can:

   - Use the same billing settings across multiple projects in your organization
   - View all projects within an organization, create teams of users, and assign teams to projects
   - Connect to Atlas as part of live migration to Atlas

### Projects
You can create multiple projects in an organization. Each project has its own Monitoring, Backup and Automations associated with the project.

Projects within the same organization share the same billing settings.

### Cluster 
In the context of MongoDB, “cluster” is the word usually used for either a replica set or a sharded cluster. A replica set is the 
replication of a group of MongoDB servers that hold copies of the same data; this is a fundamental property for production deployments as it ensures high availability and redundancy, which are crucial  features to have in place in case of failovers and planned maintenance periods.
A sharded cluster is also commonly known as horizontal scaling, where data is distributed across many servers.
The main purpose of sharded MongoDB is to scale reads and writes along multiple shards.
The minmum cluster size is three and each node is deployed into different AZ for HA
AWS customers can access Atlas through internet, VPC peering and PrivateLink

### Database
A database is the same idea as Oracle Database, except instead of having a group of tables. A Mongo Database is a container of collections

### Collection
This is equivalent to a table in Oracle.

### Document
This can be roughly viewed as a row in standard databases. The document is refered to as JSON file.

### Field
A field in a document, is like a column in a row of data in Oracle. At the end of the sign-up process, you will be prompted to create an organization and a project.





# Getting Started with MongoDB Atlas
## Step1 - Create MongoDB Cloud account
### Registration
In order to create an Atlas account, navigate to https://www.mongodb.com/cloud/atlas/register
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/886841ce-a05e-4770-8d9c-bebf465676a7)
Click Try Free

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/c055b0a1-c45c-42c4-bde4-022b8aca0309)


You can sign up using your Google account. This would be the preferred method; however, you can also register using your email address.

You will be prompted to create new organization. Enter FirstOrg as new organization name
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/3f778b7d-69ec-49d6-a35e-bc19945d079b)

Add your name as Organization Owner
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/92d7268e-47f1-4ec3-9729-3d7337bc51c0)

Click Create Organization

It will let you create project

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/db50e566-d401-4a85-8337-b594eda345ac)

Click New Project
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/a7704e75-93d7-46bd-afd5-78e3f8973e66)
Enter FirstProject as name and click Next

Add your name as Project Owner
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/6020d3cc-67bc-487d-91b1-69065f3c1d7c)
Click Create Project

## Step2 - Create MongoDB Atlas cluster
This will bring you to create cluster page
You’ll be presented with a choice of Shared Cluster, Dedicated Cluster, and Multi-Cloud & Multi-Region Cluster.

Shared Cluster is the least expensive (or free, depending on the usage) but it utilizes shared hardware resources and network.

Dedicated Cluster provides you with a dedicated set of hardware and network isolation as well as the option to scale automatically within a single region.

The Multi-Cloud & Multi-Region Cluster builds on top of what the dedicated cluster provides. It offers the best availability since it can replicate data across multiple geographic regions. It also allows the creation of multi-cloud clusters using any combination of cloud providers: AWS, Azure, and GCP.

If you’d like to explore a little with the free tier, select the Shared Cluster.
You’ll also be able to select the cluster tier and additional settings, such as turn on backup and cluster name. Some options, such as the MongoDB version cloud backups, are only available with the paid cluster tiers.

Once you are satisfied with your selection, click the Create Cluster button. It may take a couple of minutes for Atlas to launch your cluster in the selected cloud hosting provider.

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/ac66fe9b-cb05-4782-a655-ac77b72517ed)

Click Create

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/abfdea20-0a24-47e1-ada0-212e74348395)

Select M0 that is free, select AWS as provider, select us-east-1 as region. 
Enter FirstCluster as new cluster neame
Click Create to create new cluster.




## Step3 - Configure network access and create a cluster user
### Creating a Cluster User
In order to connect to the database from a script or an application, you must first create a MongoDB database user. The database user allows you to connect and use the databases. Please note this is separate from the user that logs in and manages the clusters and resources in Atlas.

Database users are created per project and have access to all the clusters in the project. You can also assign different roles and privileges to the database users. Note that the first user you create will automatically be granted administrative privileges.

Right below the network access settings, you can create a database user. First enter the username and password and then click on the Create database user button.

If you later need to add more users to the project, you can do it from the Security tab.
Now you need to configure database username and password in order to access database
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/36ee0e7d-d5c1-4aab-a069-7850bef50fe9)

Select Username and Password, enter username and password, click Create User

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/2dba13bf-1016-47b0-a250-14911cbb85ce)

### Allowing Access to Your IP Address
For security reasons, new database clusters do not have network access enabled by default. You need to enable network access explicitly by whitelisting the addresses that will connect to the cluster.

Each entry can be an IP address, a subnet, or you can enable access from any location. In general, you would grant access only to a list of subnets or IP addresses rather than grant access to any location. This limits the connections your cluster accepts, making it more secure.

To enable network access to your cluster, click on the Connect button from the clusters view in the Atlas management console. This will open up the connection settings wizard.

In order to allow access from your current IP address, click on the Add your current IP address button. If you need to access it from a different IP address or subnet, click on the Add a different IP address button and enter the IP or a subnet using the CIDR notation, such as 172.10.1.0/24.
Select My Local Environment, Add My Current IP address 
Please make sure you do not use VPN.
Click Finish and Close

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/515dbd75-ef3a-41b8-9140-f1f30073f367)
## Step4 - Connect to the cluster
Depending on your application, you may need to install a driver (library) corresponding to your platform in order to connect to a cluster in Atlas. You can see the full list of 
supported drivers here
. If you’re using 
Compass
 (the MongoDB UI application) or the 
mongo shell
 application, the drivers are already built in.

Regardless of your application, you’ll need to generate a database connection string for your cluster. If you are just creating your cluster, the last step in the process will allow you to create a connection string. Once you have enabled network access and created a database user, you can click on the Choose connection method button, which will allow you to generate a connection string for your application. You can also create the connection string by clicking on the Connect button on your cluster from the Clusters tab in Atlas.

Click Database on left panel
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/cbbc18b1-62a7-4197-91e8-bc82d97b6c4a)

Click Connect

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/86e2e802-a0d1-4266-8c91-20bbd9c81d8e)

This lab will use Mongodb Compass to connect to Atlas
Click Compass

Select operation system and download MongoDB Compass, click Download Compass. Install Compass on your computer. Open Compass

Copy the connection string and paste it into COmpass, updata the password, click Connect

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/18de3d19-a72b-4705-a2a8-7533615e794a)

You should be able to connect to Atlas.
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/4096173c-8293-4841-8ca2-247452aeff50)

## Step5 - Load data into Atlas

Atlas provide sample data set. From the cluster view in the Atlas management console, click on the ellipsis button [...] and select “Load Sample Data” from the menu. Then confirm your selection.

This will load a few sample collections that you can use to run test queries and learn more about MongoDB. You can view the sample collections loaded by clicking on the Collections button on your cluster from the Clusters tab in Atlas.
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/1f6ff1bd-3fa2-4a8d-a058-371e56da45af)

Wait for the data load finished.

## Step6 - Search data in Atlas
Move to Mongodb Compass and select Database --> sample_airbnb --> listingsAndReviews. You can see there are 5555 documents. Mongodb automatically assign _id for each document.
Now we want to find out all listing with property_type: "House". Enter {property: "House"} in the Filter and click Find
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/471c0b8e-61b5-48bc-807f-b42e308be1c2)


you will see there are 606 documents found with property_type equal to "House"
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/21737324-10e5-4773-8d18-fa7459327323)


# Congratuations! you have finished the MongoDB Atlas Tutorial lab
