> ### Step 1: Login to IBM Cloud Pak for Data

> 1. Login to IBM Cloud Pak for Data with valid credentials

To perform this lab you need IBM Cloud Pak for Data's credential which include both username and password.

![Login](/images/login.png)

> ### 2. Create new project

Click on the Navigation Menu and expend Projects and click All Projects. Then click on ‘New Project +’ to create new project by following below steps shown in images

![DV Menu](/images/project-1.png)
![DV Menu](/images/project-2.png)

Click `Create an empty project` to create empty project

![DV Menu](/images/project-3.png)

Give a name to project (eg. `Data_Fabric_Project`)

![DV Menu](/images/project-4.png)

Once the project is created, you will redirect to `Project` page as shown below

![DV Menu](/images/project-5.png)

> ### 3. Create new connections with external data sources.

> 1. Select Add to project + and choose Connection as asset type

![Create connection](/images/create_connection.png)

> 2. Choose Amazon S3 as connection type.

![Amazon S3](/images/create_connection_2.png)

> 3. Provide Amazon S3 connection details to make connection between Amazon S3 and IBM Cloud Pak for Data.

![Amazon S3 Connection](/images/amazon_s3_connection_details.png)
![Amazon S3 Connection](/images/add_connection_catalog_6.png)

> 4. Click Test connection to validate the connection. If it is successful click Create to create S3 connection.

![Amazon S3 Test Connection](/images/test_connection.png)

![Amazon S3 Test Connection](/images/s3_test_connection_success.png)

> 5. Similarly perform same step to create connection for asset type Amazon Redshift, and Amazon RDS for PostgreSQL.

![Create connection](/images/create_connection.png)

Select Amazon Redshift connector

![Data Ingestion](/images/redshift_connection_page.png)

Give a name to connection (eg `Amazon Redshift Connection`)

![Data Ingestion](/images/redshift_connection_1.png)

Again, Go to your `Project` page click `Add to project +` and choose `Connection`

![Create connection](/images/create_connection.png)

Select Amazon RDS for PostgreSQL connector

![Data Ingestion](/images/aurora_connection_page.png)

Provide connection details

![Data Ingestion](/images/aurora_connection.png)

> 6. Since we have created data source connection, now lets ingest data from connected data source. Click Add to project + and then click Connected data

![Data Ingestion](/images/choose_asset_type.png)

Click `Select source`

![Data Ingestion](/images/select_data_source.png)

Select `apotheca_healthcare_personnel_data.csv`

![Data Ingestion](/images/select_connection_source_s3.png)

Give any unique name to asset

![Data Ingestion](/images/select_connection_source_s3_1.png)

In the `Data_Fabric_Project` page you will see the recently added asset

![Data Ingestion](/images/s3_data_asset_in_project.png)

> 7. Similarly collect data from redshift data source

![Data Ingestion](/images/choose_asset_type.png)

Discover and select `actavis_pharma_healthcare_personnel_table`

![Data Ingestion](/images/redshift_asset_discovery.png)

Specify a unique name

![Data Ingestion](/images/redshift_asset_discovery_1.png)

Verify asset has been added to the project

![Data Ingestion](/images/redshift_asset_discovery_2.png)

> 8. Similarly ingest data from Amazon Aurora PostgreSQL database.

![Data Ingestion](/images/choose_asset_type.png)

Discover and select `mylan_specialty_personnel_data_table`

![Data Ingestion](/images/aurora_select_connection_source.png)

Specify a unique name

![Data Ingestion](/images/aurora_connected_data_asset.png)

Verify asset has been added to the project

![Data Ingestion](/images/aurora_connected_data_asset_1.png)


> 9. To create integration pipeline, let's click Add to project + then DataStage flow.

![DataStage](/images/datastage.png)

> 10. Enter DataStage flow name and click Create to create new DataStage flow.

![DataStage](/images/datastage_flow_1.png)

> 11. DataStage Homepage. Here you will see three options. Connectors to ingest or output to data source. Stages to perform ETL operation and Quality.

![DataStage Homepage](/images/datastage_4.png)

![DataStage Homepage](/images/datastage_5.png)

![DataStage Homepage](/images/datastage_6.png)

> 12. Click Connectors to expand and then drag and drop Asset Browsers to datastage canvas.

![DataStage Asset Browser](/images/datastage_7.png)

> 13. You need to select data assets to create integration pipeline. Select Data asset and then click all three data assets which ingested in previous step and then click Add.

![DataStage Asset Browser](/images/browse_asset.png)

> 14. You should be able to see all three data assets as shown below.

![DataStage Asset Browser](/images/browse_asset_1.png)

> 15. Now search funnel in the search box and drag and drop Funnel Stage to the canvas.

![DataStage Asset Browser](/images/funnel.png)

> 16. Create links from all data assets to Funnel Stage as shown in below picture.

![DataStage Asset Browser](/images/funnel_1.png)

> 17. Double click on all three data assets one by one and then click Output tab and then click Edit column to verify Data type, length and nullability of all columns

![DataStage Asset Browser](/images/datastage_asset.png)

![DataStage Asset Browser](/images/s3_type.png)

![DataStage Asset Browser](/images/redshift_type.png)

![DataStage Asset Browser](/images/aurora_type.png)

> 18. Search remove duplicate stage and again drag and drop the stage.

![DataStage Asset Browser](/images/remove_duplicate_stage.png)

> 19. Double click on Remove Duplicate Stage to select criteria


![DataStage Asset Browser](/images/remove_duplicate_by_id.png)

![DataStage Asset Browser](/images/remove_duplicate_by.png)

> 20. Search sort and drag and drop Sort stage. double click on sort
stage and select sort criteria by id.

![DataStage Asset Browser](/images/sort_by_criteria.png)

![DataStage Asset Browser](/images/sort_by.png)

> 21. Search rds and then drag and drop Amazon RDS for PostgreSQL connector to canvas.

![DataStage Asset Browser](/images/datastage_output_1.png)

> 22. Double click on RDS connector to specify data source and table name

![DataStage Asset Browser](/images/datastage_output_2.png)

> 23. Compile the datastage pipeline and run if compile succeeded.

![DataStage Asset Browser](/images/compile.png)

![DataStage Asset Browser](/images/compile_success.png)

![DataStage Asset Browser](/images/run_success.png)


> 25. Now we have integrated data available in Amazon RDS for PostgreSQL. Let's ingest the data from the data source

![Data Ingestion](/images/choose_asset_type.png)

Discover and select integrated table (eg. `healthcare_personnel_integrated_data_table_v1`)

![DataStage Asset Browser](/images/integrated_table.png)

Specify the name to asset

![DataStage Asset Browser](/images/integrated_table_1.png)

Verify data asset is present in the project

![DataStage Asset Browser](/images/integrated_table_2.png)
