# Multi-Tier-Website-Hosting-on-AWS-
## Project Overview

The goal of this project is to build a multi-tier web application hosted on AWS with the following components:

1. **Web Tier**: A PHP-based web application that serves the front-end user interface.
2. **Data Tier**: An RDS database instance that stores application data.
3. **Auto Scaling Group**: An Auto Scaling group that automatically scales the web tier to handle increased traffic.

## Architecture

The high-level architecture of the system is as follows:

```
+--------------+    +--------------+
|    Web Tier  |    |   Data Tier  |
|              |    |              |
|  EC2 Instances|    |   RDS MySQL  |
|   (PHP App)  |    |   Database   |
+--------------+    +--------------+
       ^                     ^
       |                     |
+--------------+    +--------------+
| Auto Scaling |    |   Load      |
|   Group      |    |   Balancer  |
+--------------+    +--------------+
       ^
       |
+--------------+
|    Users     |
+--------------+
```

1. **Web Tier**: The web tier consists of EC2 instances running a PHP-based web application. This application handles all the front-end interactions with users.

2. **Data Tier**: The data tier is an RDS MySQL database instance that stores all the application data. The web application communicates with the database to read and write data.

3. **Auto Scaling Group**: An Auto Scaling group is used to automatically scale the web tier. When the website experiences increased traffic, the Auto Scaling group will automatically launch additional EC2 instances to handle the load. When traffic decreases, it will automatically terminate instances to save costs.

4. **Load Balancer**: An Elastic Load Balancer is used to distribute incoming traffic across the EC2 instances in the Auto Scaling group.

## Implementation Steps

1. **Set up the RDS Database**: Create an RDS MySQL database instance to serve as the data tier.

2. **Deploy the PHP Web Application**: Create EC2 instances running a PHP-based web application. Configure the application to connect to the RDS database.

3. **Configure the Auto Scaling Group**: Set up an Auto Scaling group to automatically scale the EC2 instances in the web tier. Configure the desired scaling policies and triggers.

4. **Set up the Load Balancer**: Create an Elastic Load Balancer and configure it to distribute traffic across the EC2 instances in the Auto Scaling group.

5. **Test the Application**: Verify that the web application is functioning correctly and that the Auto Scaling group is able to handle increased traffic.


