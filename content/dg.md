> ### 1. Create Rules for Data Masking and Obfuscating

> 1. Click navigation menu then expand Governance and then click Rules.

![Data Ingestion](/images/governance_1.png)

> 2. Click Add rule -> New rule

![Data Ingestion](/images/rules.png)

Select `Data protection rule`

![Data Ingestion](/images/governance_3.png)

> 3. Add rule for Email Address masking. Select `Data Class` as `Email Address` to `Redact` the data as shown in image below

![Data Ingestion](/images/rules_1.png)

Once Rule has been created, you can see it in `Rules` page

![Data Ingestion](/images/governance_9.png)

> 4. Create rule for last name obfuscation

![Data Ingestion](/images/rules.png)

Select `Data protection rule`

![Data Ingestion](/images/governance_3.png)

Select `Data Class` as `Last Name` to `Obfuscate` the data as shown in image below

![Data Ingestion](/images/governance_10.png)

Once Rule has been created, you can see it in `Rules` page as well.

![Data Ingestion](/images/governance_11.png)

> 5. Go to navigation menu and expand `Governance` and then click `Categories` create category.

![Data Ingestion](/images/governance_13.png)

Click `Add category`

![Data Ingestion](/images/governance_14.png)

Give a name (eg `PII_CATEGORY`)

![Data Ingestion](/images/governance_15.png)

Once Category has been created you will be redirected to newly created PII_CATEGORY page.

![Data Ingestion](/images/governance_16.png)

> 6. Click navigation menu then expand Governance and then click `Business Term` to create a new Business Term.

![Data Ingestion](/images/governance_24.png)

Click `Add business term`

![Data Ingestion](/images/governance_23.png)

Give a name to business term and attach category to it.

![Data Ingestion](/images/governance_25.png)

Publish Business Term

![Data Ingestion](/images/governance_26.png)

> 7. Go to navigation menu and expand `Governance` and then click `Policy` to create new policy.

![Data Ingestion](/images/governance_17.png)

Create Policy and attach PII_CATEGORY to the policy.

![Data Ingestion](/images/governance_18.png)

> 8. Add both rules in Data Protection rules of Policy and then add business term as well to this policy and Publish Policy.

![Data Ingestion](/images/governance_22.png)


> 9. Go back to catalog and open reshaped asset and then click on `plus (+)` icon in the `Governance artifacts` ->`Business terms` as showm in below image.


![Data Ingestion](/images/catalog_governance.png)

Select Pii_Business_Term to the catalog

![Data Ingestion](/images/catalog_governance_1.png)

Verify business term has been added to the catalog

![Data Ingestion](/images/catalog_governance_2.png)

> 10. Go back to the catalog which you have created and click `Access control` tab and click `Add collaborators +`

![](/images/add_user_to_catalog_1.png)

> 11.Add datascientist user which might have received during this lab as collaborator with `Viewer` role.

![](/images/add_user_to_catalog_2.png)

With the above all steps you have successfully created data masking and obfuscating rules to protect sensitive data. also with the last step you have provided access of governed data to data scientist. Now let's follow below steps to see whether data scientist receive masked data or not.

> 12. Login using datascientist or developer credential to see masked Email Address and obfuscated last name.

![Data Ingestion](/images/governance_49.png)
