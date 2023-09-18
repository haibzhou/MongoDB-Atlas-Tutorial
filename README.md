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

This will bring you to create cluster page
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/ac66fe9b-cb05-4782-a655-ac77b72517ed)

Click Create

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/abfdea20-0a24-47e1-ada0-212e74348395)

Select M0 that is free, select AWS as provider, select us-east-1 as region. 
Enter FirstCluster as new cluster neame
Click Create to create new cluster.

Now you need to configure database username and password in order to access database
![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/36ee0e7d-d5c1-4aab-a069-7850bef50fe9)

Select Username and Password, enter username and password, click Create User

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/2dba13bf-1016-47b0-a250-14911cbb85ce)
Select My Local Environment, Add My Current IP address 
Please make sure you do not use VPN.
Click Finish and Close

![image](https://github.com/haibzhou/MongoDB-Atlas-Tutorial/assets/109695471/515dbd75-ef3a-41b8-9140-f1f30073f367)












## Step2 - Create MongoDB Atlas cluster
## Step3 - Configure network access and create a cluster user
## Step4 - Connect to the cluster
## Step5 - Load data into Atlas
## Step6 - Search data in Atlas
## Step7 - Insert/update data in Atlas
