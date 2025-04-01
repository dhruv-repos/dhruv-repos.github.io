---
title: RDS in AWS
layout: home

---

# Amazon Relational Database Service 
Web service to operate a relational database in the cloud.
RDS is responsible for **hosting** the *software components* and *infrastructure* DB instances .
User is responsible for **Query Tuning**.

## RDS DB instances
- Isolated database environment in AWS cloud.
- DB instance can contain multiple user-made databases
- DB instance classes
    - Determines the computation and memory capacity of a DB instance
    - General purpose , Mem or Compute optimised, Burstable performance
        - *Burstable* : provides baseline level of CPU performance that can burst to higher level using credits earned during low utilisation
- DB instance storage
    - SSD, Provisioned IOPS , Magnetic
### DB Clusters
    write about multi az db cluster deployments

-----------------
## Snapshots & Backups
- Backups are automated point in time recovery of the DB instance. Need to specify **Retention Period** : sets how far we can recover our database
- Snapshots are manual
----------------
## Subnet Groups
 - A DB subnet group is a collection of subnets (typically private) that you create in a VPC and that you then designate for your DB instances. By using a DB subnet group, you can specify a particular VPC when creating DB instances using the AWS CLI or RDS API. 
 - Minimum of 2 Avaliability Zones required

## Parameter Groups
 - A DB parameter group acts as a container for engine configuration values that are applied to one or more DB instances.

DB cluster parameter groups apply to Multi-AZ DB clusters only. In a Multi-AZ DB cluster, the settings in the DB cluster parameter group apply to all of the DB instances in the cluster. 

  - For MySQL : find the parameter groups as **server system variables**. They define the behaviour and properties of the MySQL server
- *Static* : these parameter changes take effect after manual reboot of the db instance.
- *Dynamic* : these paramter changes take effect immediately and no reboot is required

## Option Groups
- An option group can specify features, called options, that are available for a particular Amazon RDS DB instance. Options can have settings that specify how the option works

These are additional features not avaliable in parameter groups

## Important Configuration settings in AWS console for RDS
### RDS Extended Support
- Paid service
- Offers to run a engine version which has reached its end of life.
### Templates
-   Production , Dev/Test , Free tier
-   Pre-selected settings as per template 
-   production has highest speed storage classes, Multi az db cluster and delete protection enabled

>  - Try not to use auto-generated passwords , make the passwords manually. If needed add them to secrets manager later on
> - In the VPC of the DB enable port ``` 3306 ``` in the security groups. Use ip address ``` 0.0.0.0/0 ``` for tcp from anywhere or simply add the ip of the private EC2 instance , which is connected to the bastion host.
> - Enable log exports for all required logs

### Additional Configuration
Choose the options for the DB that would be created inside this instance

#### DB cluster parameter group
use "Cluster type" for cluster and "Parameter" type for instance when creating a custom parameter group

> **IMPORTANT** : When using the MySQL engine use create a custom parameter group before hand and use it.
The custom parameter group should have the following :
>- ```general_log``` = 1
>- ```log_output``` = FILE [Donot Use Table type]
>- ```slow_query_log``` = 1

> ***Disable Delete Protection*** to be able to delete the DB Instance later on




