# Data Access and Governance using CPD on AWS

In this Code Pattern, we will demonstrate how to create hybrid cloud data architecture using IBM Cloud Pak for Data (CP4D) and AWS together.

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

## Include Components

These are the components & services which are included in this Code Pattern.

* [IBM Cloud Pak for Data](https://www.ibm.com/in-en/products/cloud-pak-for-data): IBM Cloud Pak for Data is a data and AI platform with a data fabric that makes all data available for AI and analytics, on any cloud.

* [IBM DataStage](https://www.ibm.com/products/datastage/) Integration tool that helps you design, develop and run jobs that move and transform data.

* [IBM Data Refinery](https://www.ibm.com/cloud/data-refinery): IBM Data Refinery is a cloud service that provides a self-service data preparation client to transform raw data into data ready for analytics.

* [IBM Watson Knowledge Catalog](https://www.ibm.com/in-en/cloud/watson-knowledge-catalog): Activate business-ready data for AI and analytics with intelligent cataloging, backed by active metadata and policy management.

* [Amazon S3](https://aws.amazon.com/s3/): Amazon Simple Storage Service (Amazon S3) is an object storage service offering industry-leading scalability, data availability, security, and performance.

* [Amazon Redshift](https://aws.amazon.com/redshift/): Accelerate your time to insights with fast, easy, and secure cloud data warehousing at scale.

* [Amazon Aurora](https://aws.amazon.com/rds/aurora/): Designed for unparalleled high performance and availability at global scale with full MySQL and PostgreSQL compatibility
