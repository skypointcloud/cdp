# CLV Prediction Sample Guide

This guide will walk you through an end to end example of CLV prediction in **Insights** using the data provided below. All data used in this guide is not real customer data and is a part of the Contoso dataset found in the SalesDemo instance.

## Step 1 - Import Customer & Online Purchase Data
Follow the steps below to import customer data from eCommerce platform:
1. Create a dataflow named eCommerce, and choose the Azure Data Lake Gen 2 connector.
2. Enter the credentials for the storage account where the csv files are stored and click on connect. Select the two eCommerce customer data and online purchase data in csv files.
3. Then, first click on the file named **eCommerceContacts.csv** and you will see a preview field table pop up on the screen.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/previewfield.PNG?raw=true)

4. Update the datatype for the columns listed below:
    - **DateOfBirth** : Date
    - **CreatedOn** : DateTime
5. Then, click on the file named **eCommercePurchases.csv** and you will see a preview field table pop up on the screen.
6. Update the datatype for the columsn listed below:
    - **PurchasedOn** : DateTime
    - **TotalPrice** : Int64
7. Select the datetime format for both the files as **11/25/1979**.
8. Click on **Save** and then run it by clicking on the three dot button and selecting Run.

## Step 2 - Import Loyalty Data
Follow the steps below to import the loyalty data from eCommerce platform:
1. Create a dataflow named loyalty, and choose the Azure Data Lake Gen 2 connector.
2. Enter the credentials for the storage account where the csv files are stored and click on connect. Select the loyalty data.
3. Then click on the file named **loyaltyCustomerData.csv** and you will see a preview field table pop up on the screen.
4. Update the datatype for the columns listed below:
    - **DateOfBirth** : Date
    - **RewardsPoints** : Int64
    - **CreatedOn** : DateTime
5. Select the datetime format for both the files as **11/25/1979**.
6. Click on **Save** and then run it by clicking on the three dot button and selecting Run.

## Step 3 - Stitch Process : Map

1. After importing the data, we now begin the Map process in the stitch section of our platform as the first step to create a customer profile.
2. Navigate to **Stitch** > **Map** and click on Select Entities.
3. Select the eCommerce Contacts Data entity and eCommerce Loyalty Data entity.
4. Click on contacts entity and complete the mapping for the various required fields.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/ecommercecontactsmapping.PNG?raw=true)

5. Click on loyalty data entity and complete the mapping for the various required fields.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/loyaltymapping.PNG?raw=true)

6. Click on Save and after the UI shows **Saved successfully**, click on Run to start the map process.

## Step 4 - Stitch Process : ML Match

1. After running the map stage of the stitch process, navigate to **Stitch** > **ML Match**.
2. Click on **Set Order** and select the data completeness  and match confidence threshold of 0.75 each.
3. Then, select the FullName and the emailAddress as the criterial column to be used while matching. If you wish, you can click on the exact match function to match records based on an exact match for email address.
4. Then click on Save and after the UI shows **Saved successfully**, click on Run to start the ML Match process.
5. Once the ML Match is done, you will be able to see the number of unique records and many other numerical representations of the output of the ML match.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/sampleguidemlmatch.PNG?raw=true)

## Step 5 - Stitch Process : ML Merge

1. After running the map and ML match, navigate to **Stitch** > **ML Merge**.
2. Click on Save and after the UI shows **Saved successfully**, click on Run to start the ML Match process.
3. Once ML Merge is done, go to the home page and look at the dashboard. You will be able to see the profile count.
4. To check the profiles, navigate to **Insights** > **Profiles**.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/sampleguideprofiles.PNG?raw=true)

## Step 6 - Create a Transactional Churn Prediction Model

With the stitch process done, we can run the clv prediction.
Below are the necessary steps required to run the prediction.
1. Go to **Insights** > **Predictions** and select to use the Customer Lifetime Value Model.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvmodelstep1.PNG?raw=true)

2. A new pop up will open on the right side of the page.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/popup.PNG?raw=true)

3. Name this model and the Output entity name to distinguish them from other models or entities.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvmodelstep2.PNG?raw=true)

4. Select Next.
5. Define model preferences
    - Set a Prediction time period to define how far into the future you want to predict the CLV. By default, the unit is set as months. You can change it to years to look further in the future.
    - Specify what Active customers mean for your business. Set the time frame in which a customer must have had at least one transaction to be considered active. The model will only predict CLV for active customers.
        - **Let model calculate purchase interval (recommended)**: The model analyzes your data and determines a time period based on historical purchases.
        - **Set interval manually**: If you have a specific business definition of an active customer, choose this option and set the time period accordingly.
    - Define percentile of High-value customer to enable the model to provide results that fit your business definition.
        - **Model calculation (recommended)**: The model analyzes your data and determines what a high value customer might be for your business based on your customers’ transaction history. The model uses a heuristic rule (inspired by the 80/20 rule or pareto principle) to find the proportion of high-value customers. The percentage of customers that contributed to 80% cumulative revenue for your business in the historical period are considered high-value customers. Typically, less than 30-40% customers contribute to 80% cumulative revenue. However, this number might vary depending on your business and industry.
        - **Percent of top active customers**: Define high-value customers for your business as a percentile of top active paying customers. For example, you can use this option to define high-value customers as top 20% of future paying customers.

        ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvmodelstep3.PNG?raw=true)

    - Select Next to proceed to the next step.
6. Add required data
    - In the Required data step, select Add data for Customer transaction history and choose the entity that provides the transaction history information as described in the prerequisites.
    - Map the semantic fields to attributes within your purchase history entity and select Next.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvmodelstep5.PNG?raw=true)

7. Add optional data
    - In the Additional data (optional) step, select Add data. Choose the customer activity entity that provides the customer activity information as described in the prerequisites.
    - Map the semantic fields to attributes within your customer activity entity and select Next.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvmodelstep7.PNG?raw=true)

8. Set update schedule:
    - In the Data update schedule step, choose the frequency to retrain your model based on the latest data. This setting is important to update the accuracy of predictions as new data is ingested in audience insights. Most businesses can retrain once per month and get a good accuracy for their prediction.
    - Select Next.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep8.PNG?raw=true)

9. Review and run the model configuration:
    - In the Review your model details step, validate the configuration of the prediction. You can go back to any part of the prediction configuration by selecting Edit under the shown value. You can also select a configuration step from the progress indicator.
    - If all values are configured correctly, select Save and run to start running the model. On the My predictions tab, you can see the status of the prediction process. The process may take several hours to complete depending on the amount of data used in the prediction.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvmodelstep8.PNG?raw=true)