
> ### Step 1: Ensure IBM Data Virtualization service is enabled and provisioned

> 1. Login to IBM Cloud Pak for Data with valid credentials

To perform this lab you need IBM Cloud Pak for Data's credential with admin role. Credentials include both username and password.

![Login](/images/login.png)

> 2. Validate if IBM Data Virtualization service is installed and provisioned

Follow the below steps to make sure IBM Data Virtualization service service is installed and provisioned in the provided IBM Cloud Pak for Data instance.

`Steps:`

1. Go to hamburger navigation menu and click on services and then click on services catalog to see all available services for this instance

![DV Install Check](/images/dv_install_check.png)

2. Now in the search box type `Data Virtualization` to search Data Virtualization (DV) service and click on it.
![DV Search Service Catalog](/images/service_catalog_dv.png)

3. Inside DV service you should be able to see that the service is enabled as shown in above picture.
![DV Service Status](/images/dv_service_status.png)

4. Now click on `Instances` to verify if `Data Virtualization` service is running.
![DV Health Status](/images/dv_health.png)

> ### 2. Create New Connection

In this step we will to create connection between external data sources and Data Virtualization service using CP4D connectors. In this lab, you will create connection with `Amazon S3`, and `Amazon RDS` data sources. Follow the below steps to create connection with those data sources:

> 1. Click Navigation Menu expand 'Data' and then click 'Data Virtualization'

![DV Menu](/images/dv_1.png)

> 2. In the Data Virtualization Page, Click Add connection + New Connection.

![DV Homepage](/images/dv_2_new.png)

![Amazon Aurora Connection](/images/dv_4.png)

> 3. Select 'Amazon RDS for PostgreSQL' connection type and fill the details to create Amazon Aurora PostgreSQL Connection in Data Virtualization then click on Create. You can also specify any name to the connection and note it down for future reference.

![Amazon Aurora Connection](/images/DV_Create_Aurora_Connection_Option.png)

![Amazon Aurora Connection Details](/images/dv_5.png)

> 4. Click skip

![Skip](/images/skip.png)

> 5. Similarly add Amazon S3 datasource by selecting connection type 'Amazon S3' and fill connection details. Similar to previous connection, You can also specify any name to the connection and note it down for future reference

> 6. Once you create both data sources connection successfully, you should see both Amazon S3 and Amazon RDS PostgreSQL connection listed on the Data sources page as shown below.

![Connection List](/images/connection_list_new.png)

> ### 3. Create virtual tables

Congratulations! In the previous step you have successfully created connection between external data sources and `Data Virtualization` service. now you can select table and file from the connection and create Virtualized tables or objects. Once tables are virtualized you can create VIEW using those virtual tables.

> 1. Open the Data Virtualization menu and click on Virtualization to expand and then click Virtualize as shown below.

![Virtualize Menu](/images/virtualize_menu.png)

> 2. You might see several tables under Tables tab which are coming from various connections. Select the tables (ts_wallonia_region_table and ts_flanders_region_table) to create virtual tables. You can also search for or filter the tables. When selected, click Add to cart, then View cart.

![Create Virtual Table](/images/create_virtual_table.png)

>3. As shown in this screen, Select the `Virtualize Data` option and provide any unique names to table (in the image below names are ts_wallonia_region_table and ts_flanders_region_table) and note it down for future reference.

Now click on the `Modify columns` of first table (here `ts_wallonia_region_table`) to verify name, type and length of the columns matches with image below and click `Apply`.

Repeat the same step for another table (here `ts_flanders_region_table`).

Once after making the changes click Apply and then click `Virtualize` in `Review cart and virtualize table` page.

![Create Virtual Table Options](/images/virtualize_1.1.png)
![Create Virtual Table Options](/images/virtualize_1.2.png)
![Create Virtual Table Options](/images/virtualize_1.3.png)

> 4. Click `Continue` to create Virtual tables.

![Create Virtual Table Confirmation](/images/create_virtualize_table_confirmation.png)

![Create Virtual Table Confirmation 1](/images/create_virtualize_table_confirmation_1.png)

> 5. In the last step we Virtualized the tables coming from Amazon RDS connection, now let's use csv file coming from Amazon S3 connection and Virtualize it. Click `Files` tab in the `Virtualize` page as shown below and then click `Endpoint`

![Virtualize Menu](/images/virtualize_file.png)

>6. Navigate to regional folder inside parent bucket and select ts-Brussels-grouped-21-04.csv as shown in below image and then click `Add to cart` then `View Cart`

![Virtualize Menu](/images/virtualize_file_1.1.png)

> 7. In the `Review cart and virtualize page` specify unique name to the table and note it down for future reference, and then click `Modify columns` button to review columns metadata.

![Virtualize Menu](/images/virtualize_file_3.1.png)

> 8. Edit the column name, type, and length as shown in below image and then click `Apply`

![Virtualize Menu](/images/virtualize_file_3.2.png)

> 9. In the `Review cart and virtualize page` check `Virtualized data` option then click `Virtualize` button.

![Virtualize Menu](/images/virtualize_file_3.3.png)

> 10. Click `Continue` to create Virtual tables.

![Create Virtual Table Confirmation](/images/create_virtualize_table_confirmation.png)

> 11. Click View virtualized data

![Virtualize Menu](/images/virtualize_file_3.4.png)

> ### 4. Create VIEW by joining two virtual tables/objects
Till now we have created connections with external data sources and from external data sources we picked tables and files to Virtualize them. Now we will use those Virtualize tables/objects and join them to create a VIEW. This VIEW will give us capability to query multiple data sources without creating data replicas.

You can follow below steps to create VIEW:

> 1. Click `Data Virtualization` menu and expand `Virtualization` and then click `Virtualized Data` option.

![Virtualized Data Menu](/images/view_menu.png)

> 2. Select the virtual tables which you have created in the previous step. (eg here `ts_wallonia_region_table` and `ts_flanders_region_table`) and click Join.

![Select Tables](/images/Join_View_1.1.png)

> 3. Join two tables by specify join key and then click on Preview to preview joined table.

![Select Tables](/images/Join_View_1.2.png)

> 4. Close preview page, click `Next` on `Join virtual objects` page

![Select Tables](/images/Join_View_1.3.png)

> 4. Edit the column names as shown in below image.

![Edit Column](/images/Join_View_1.4.png)

> 5. Once after ensuring all details, provide unique view name (eg. flanders_wallonia_joined_view), select `Virtualized data` checkbox and click `Create view`.

![Select Tables](/images/Join_View_1.5.png)

> 6. Click 'Virutalized Data' and Select joined view you created in previous step (eg. flanders_wallonia_joined_view) and ts_brussels_region_table table to create view.

![Select Tables](/images/Join_View_1.6.png)

![](/images/Join_View_1.7.png)

> 7. Specify `date` as join Key and click `Preview`

![](/images/Join_View_1.8.png)

![](/images/Join_View_1.9.png)

> 8. Edit the column names as shown below

![](/images/Join_View_1.10.png)

> 9. Specify the view name (eg. `brussels_wallonia_flanders_joined_view`) and click `Create view`

![](/images/Join_View_1.11.png)

By following all the steps you have created a single joined view from different data source. Now let's go to the `Catalog` to view the data.

> 10. Click navigation bar and expand `Catalogs` and click All Catalogs and select `default catalog` to see the view we created in last step.

![Select Tables](/images/catalog_menu.png)

> 11. In the `Default Catalog` page you will see the joined view (brussels_wallonia_flanders_joined_view) which you have created in the last step. If you noticed view started from `ADMIN.` which is the username. In your case, it might start with `<USER_NAME>.brussels_wallonia_flanders_joined_view`.

Click on the view for more details.

![](/images/joined_view_1.png)

> 12. Click `Assets` tab and provide your Cloud Pak for Data admin credentials.

![](/images/joined_view_2.png)
![](/images/joined_view_3.png)

> 13. After successfully validating credentials, you will be able to see the integrated data.

![](/images/joined_view_4.png)

> 14. Click on the `Profile` tab to get statistics of data inside view.

![](/images/joined_view_5.png)
