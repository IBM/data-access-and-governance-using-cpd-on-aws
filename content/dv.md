
> ### Step 1: Ensure IBM Data Virtualization service is enabled and provisioned

> 1. Login to IBM Cloud Pak for Data with valid credentials

To perform this lab you need IBM Cloud Pak for Data's credential with admin role. Credentials include both username and password. If you do not have the credentials then ask the lab instructor to provide one.

![Login](/images/login.png)

> 2. Validate if IBM Data Virtualization service is installed and provisioned

Follow the below steps to make sure IBM Data Virtualization service service is installed and provisioned in the provided IBM Cloud Pak for Data instance.

`Steps:`

1. Go to hamburger navigation menu and click on services and then click on services catalog to see all available services for this instance

![DV Install Check](/images/dv_install_check.png)

2. Now in the search box type data virtualisation to search data virtualization service and click on it.

3. Inside data virtualisation service you should be able to see that the service is enabled as shown in above picture. If it is not, ask the lab instructor and get data virtualisation service enabled.

4. Now click on instances and the status of the data virtualisation instance to verify if Data virtualisation service is running without any issues.

> ### 2. Create New Connection

Click the Navigation Menu and select Data Virtualization. Then click on ‘Add connection’ to create data sources as connection in Data Virtualization. In this lab you will create connection with Amazon S3, and Amazon RDS data sources.

> 1. Click navigation menu expand 'Data' and then click 'Data Virtualization'

![DV Menu](/images/dv_1.png)

> 2. Click Add connection + then click new connection.

![DV Homepage](/images/dv_2.png)

![Amazon Aurora Connection](/images/dv_4.png)

> 3. Select 'Amazon RDS for PostgreSQL' connection type and fill the details provided by Instructor to create Amazon Aurora PostgreSQL Connection in Data Virtualization then click on Create.

![Amazon Aurora Connection](/images/DV_Create_Aurora_Connection_Option.png)

![Amazon Aurora Connection Details](/images/dv_5.png)

> 4. Click skip

![Skip](/images/skip.png)

> 5. Similarly add Amazon S3 datasource by selecting connection type 'Amazon S3' and fill connection details provided by instructor.

> 6. Once The data connections are added as a data source for Data Virtualization, and you should see the Amazon S3 and Amazon RDS PostgreSQL connection listed on the Data sources screen.

![Connection List](/images/connection_list.png)

> ### 3. Create virtual tables and views using data virtualization

Congratulations! You have successfully added data sources to data virtualization. now you can virtualize the table within the data virtualization. Once tables are virtualized you can create VIEW using those virtual tables.

> 1. Open the Data Virtualization menu and click on Virtualization to expand and then click Virtualize.

![Virtualize Menu](/images/virtualize_menu.png)

> 2. You might see several tables under Tables tab. Select the tables (ts_wallonia_region_table and ts_flanders_region_table) to create virtual tables. You can also search for or filter the tables. When selected, click Add to cart, then View cart.

![Create Virtual Table](/images/create_virtual_table.png)

> 3. In this screen, You need to choose whether you want to assign the virtualized data to a data request, a project, or to the virtualized data. Select the Virtualize Data option and provide a unique table name and then click Virtualize to create Virtual table.

![Create Virtual Table Options](/images/virtualize_1.png)

> 4. Click on confirmation to create Virtual tables.

![Create Virtual Table Confirmation](/images/create_virtualize_table_confirmation.png)

![Create Virtual Table Confirmation 1](/images/create_virtualize_table_confirmation__2.png)

> 5. Now it is time to create the joined VIEW by joining two virtualized tables/objects. This will allow you to query multiple data sources without copying or moving the data. To create VIEW we need to join two virtual tables which we created in the previous step.
Let's click on Data Virtualization menu and expand Virtualization and then click Virtualized Data option.

![Virtualized Data Menu](/images/view_menu.png)

> 6. Select the virtual tables which you have created in the previous step. (eg here ts_wallonia_virtual_table and ts_flanders_virtual_table) and click Join.

![Select Tables](/images/Join_View.png)

> 7. After selecting the tables and click Join.

![Select Tables](/images/Join_View.png)

> 8. Join two tables by specify join key and then click on Preview to preview joined table.

![Select Tables](/images/join_view_1.png)

![Select Tables](/images/preview.png)

> 9. If you see above result on preview, then click Next and edit column name as shown in below image. Then click Next.

![Edit Column](/images/edit_column_1.png)

> 10. Once after ensuring all details, provide unique view name (eg. FLANDERS_WALLONIA_MERGED_VIEW_V1) and click Create View.

![Select Tables](/images/create_view_final_v1.png)

> 11. Go back to 'Virutalized Data' menu and Select joined view you created in previous step (eg. FLANDERS_WALLONIA_MERGED_VIEW_V1) and brussels table to create view.

![Select Tables](/images/virtualized_view_1.png)

![Select Tables](/images/virtualized_view_2.png)

![Select Tables](/images/virtualized_view_3.png)

> 12. in the above preview, there are multiple duplicate region string. So, let's customize SQL query.

![Select Tables](/images/sql_query.png)

![Select Tables](/images/sql_query_1.png)

> 13. Once after all steps are performed, you will see below view in 'Virtualized Data' option.

![Select Tables](/images/final_view.png)

> 14. Publish the view to Catalog where you can govern the view using IBM Watson Knowledge Catalog. You will learn more about governance and data protection (masking) in Governance lab.

![Select Tables](/images/publish.png)

![Select Tables](/images/publish_1.png)

> 15. Click navigation bar and expand Catalogs and click All Catalogs and select default catalog to see the view we created in last step.

![Select Tables](/images/catalog_menu.png)

![Select Tables](/images/catalog_dv.png)
