# Data Access and Governance using CPD on AWS

In this Code Pattern, we will demonstrate how to create hybrid cloud data architecture using IBM Cloud Pak for Data (CP4D) and AWS together. This Code Pattern has four tutorials covering different features of the IBM services on AWS environment. 

`Data fabric` is a highly scalable, distributed data architecture comprising both shared data assets and streamlined data integration and governance capabilities that can be used to tackle modern data challenges. A typical data fabric solution will comprising of components such as Data Catalog, Data Integration, Data Governance, Data Visualisation etc.

In this Data Access & Governance Code Pattern, you will solve the challenges faced by different personas in Data Analytics.

* Data scientists spend 80% of their time in discovering, curating, and cleansing the data. How to provide them quality data for analytics?
* Data Engineers face lots of challenges while integrating data from multiple data sources. How can they quickly and efficiently collect and integrate data?
* Data Steward deals with data privacy and protection challenges. How to ensure that the data is governed, and no sensitive information is shared with data consumers?

These Gaps could now be addressed by the governed data fabric architecture using IBM Cloud Pak for Data.

After completing this Code Pattern, you will understand how to :
* How to create connection between external data sources and IBM Cloud Pak for Data.
* How to ingest data from multiple data sources.
* How to clean, filter, or reshape data.
* How to query data from multiple data sources without copying or moving the data.
* How to create data integration pipeline to transform and integrate data from heterogeneous data sources.
* How to protect sensitive data (such as PII) to be shared with data consumers.
* How to schedule job to run data integration pipeline periodically.

## Architecture

![architecture](/images/lab2-ref-architecture.png?classes=shadow)

## Flow

1. Create external connection between external data sources (eg. Amazon S3, and Amazon Aurora PostgreSQL) and IBM Cloud Pak for Data.
2. Use IBM Data Virtualization to query data from multiple data sources without creating data replica.
3. Use IBM DataStage to create ETL pipeline
4. Use IBM Data Refinery Flow to clean, and filter the data.
5. Use IBM Watson Knowledge Studio to profile and govern the data.
6. Supply the data to AI based predictive system such as Amazon SageMaker or Jupyter Notebook to create machine learning models.

## Video

[![](http://img.youtube.com/vi/KlSru4U46tk/0.jpg)](https://youtu.be/KlSru4U46tk)

## Include Components

These are the components & services which are included in this Code Pattern.

* [IBM Cloud Pak for Data](https://www.ibm.com/in-en/products/cloud-pak-for-data): IBM Cloud Pak for Data is a data and AI platform with a data fabric that makes all data available for AI and analytics, on any cloud.

* [IBM DataStage](https://www.ibm.com/products/datastage/) Integration tool that helps you design, develop and run jobs that move and transform data.

* [IBM Data Refinery](https://www.ibm.com/cloud/data-refinery): IBM Data Refinery is a cloud service that provides a self-service data preparation client to transform raw data into data ready for analytics.

* [IBM Watson Knowledge Catalog](https://www.ibm.com/in-en/cloud/watson-knowledge-catalog): Activate business-ready data for AI and analytics with intelligent cataloging, backed by active metadata and policy management.

* [Amazon S3](https://aws.amazon.com/s3/): Amazon Simple Storage Service (Amazon S3) is an object storage service offering industry-leading scalability, data availability, security, and performance.

* [Amazon Redshift](https://aws.amazon.com/redshift/): Accelerate your time to insights with fast, easy, and secure cloud data warehousing at scale.

* [Amazon Aurora](https://aws.amazon.com/rds/aurora/): Designed for unparalleled high performance and availability at global scale with full MySQL and PostgreSQL compatibility

## Featured Technologies

* [Data Fabric](https://www.ibm.com/in-en/analytics/data-fabric/): A data fabric is an architectural approach to simplify data access in an organization to facilitate self-service data consumption.
* [Analytics](https://developer.ibm.com/technologies/analytics/): Uncover insights with data collection, organization, and analysis.
* [Data Management](https://developer.ibm.com/technologies/data-management/): Organize and maintain data processes through the information lifecycle.
* [Data Privacy](https://developer.ibm.com/technologies/data-privacy/): Using user data responsibly.

## Data Access and Governance Use-cases

This code pattern covers two use-cases per below. 

![Select Tables](/images/demo.png)

# Data Virtualization Tutorial

Research shows that up to 68% of data is not analyzed in most organizations and up to 82% of enterprises are inhibited by data silos Data silos are one of the common problems which delays Data Analytics in most of the organizations. One of the primary reason why organizations delay data analytics is due to Data Silos challenges. Enterprise data spreads across multiple data sources, so Data Engineers face challenges to integrate data from various different kinds of data sources.

In this tutorial, you will learn how to solve data silos challenges without copying or moving data using the Data Virtualization service offered by IBM Cloud Pak for Data.

Data Virtualization(DV) refers to the process of abstracting heterogeneous data sources into a single data access layer which delivers integrated data to users or applications. DV allows you to query data from multiple data sources without creating data replicas.

In this Data Virtualization tutorial we will create connections between external data sources and IBM Data Virtualization service and then you will create a single virtualized view by joining data from different data sources such as Amazon S3 and Amazon Aurora PostgreSQL.

In addition to that you will also learn how to govern and protect virtualized views using IBM Watson Knowledge Catalog to avoid data protection and data privacy issues.

### Learning Objectives:
> #### In this tutorial you will learn:
> 1. How to make a connection between external data sources & IBM Data Virtualization service
> 2. How to virtualize the data and create a single, joined VIEW.

### Learning Outcome:
At the end of the tutorial you will be able to create a VIEW to query data from multiple data sources without creating data replica. This solves data silos challenges faced by enterprises which force them to copy the data into centralized repository for analytics.

### Prerequisites:
> 1. IBM Cloud Pak for Data
> 2. Data Virtualization on IBM Cloud Pak for Data
> 3. External Data Sources (Amazon S3, Amazon Aurora PostgreSQL)
> 4. IBM Watson Knowledge Catalog

### Estimated time:
It should take you approximately 15-20 minutes to complete this tutorial.

[Click here to get the detailed steps to execute this tutorial](/content/dv.md)

### Summary

In this tutorial you have learned how to use Data Virtualization on IBM Cloud Pak for Data to virtualize data and create merged VIEW to query multiple data sources without moving or copying the data.

# Data Integration Tutorial 

ETL breaks down data silos and empowers enterprises to integrate data from multiple data sources into a single repository of well-formatted data.

IBM DataStage® on IBM Cloud Pak for Data enables you to create, manage, load and run DataStage jobs to perform seamless data integration from disparate data sources to yield insightful information. IBM DataStage utilized the common ETL concepts such as flows, jobs, projects, connections, environments etc.

## Learning Objectives:
> #### In this tutorial you will learn:
> 1. How to make a connection between external data source and IBM Cloud Pak for Data
> 2. How to create ETL pipeline using IBM DataStage
> 3. How to create scheduling rule to create data integration pipeline.

## Prerequisites
> 1. IBM Cloud Pak for Data
> 2. IBM DataStage
> 3. External Data Sources (Amazon S3, Amazon Aurora PostgreSQL)
> 4. IBM Watson Knowledge Catalog

## Estimated time
It should take you approximately 15 minutes to complete this lab.

[Click here to get the detailed steps to execute this tutorial](/content/ds.md)

## Summary

In this tutorial, you have learned how to create connection with Amazon S3, RDS, and Redshift and how to collect data from these data sources. Also we learned that how to create ETL pipeline using IBM DataStage.

# Data Cleansing & Reshaping tutorial

In this tutorial, you will learn how to clean and reshape data using IBM Data Refinery flow.

## Learning Objectives:
> #### In this tutorial you will learn:
> 1. How to filter data based on age criteria
> 2. How to visualize data

## Prerequisites
> 1. IBM Cloud Pak for Data
> 2. IBM Data Refinery
> 3. External Data Sources (Amazon S3, Amazon Aurora PostgreSQL)
> 4. IBM Watson Knowledge Catalog

## Estimated time
It should take you approximately 15 minutes to complete this lab.

[Click here to get the detailed steps to execute this tutorial](/content/dr.md)

## Summary

This lab you have learned how to clean or reshape the data using IBM data refinery. Also we have learned how to create catalog and how to export data from project to catalog.
