# Product Recommendation Prediction

This guide will walk you through an end to end example of Product Recommendation prediction in **Insights** using the data provided below. All data used in this guide is not real customer data and is a part of the Contoso dataset found in the SalesDemo instance.

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

## Step 6 - Create a Product Recommendation Prediction

With the stitch process done, we can run the Product Recommendation.
Below are the necessary steps required to run the prediction.
1. Go to **Insights** > **Predictions** and select to use the Product Recommendation.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvmodelstep1.PNG?raw=true)

2. A new pop up will open on the right side of the page.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/popupforproductrecommendation.PNG?raw=true)

3. Name this model and the Output entity name to distinguish them from other models or entities.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/step1forproductrecommendation.PNG?raw=true)

4. Select Next.
5. Define model preferences
    - Set the Number of products you want to recommend to a customer. This value depends on how your delivery method fills data. If you can recommend three products, set this value accordingly.
    - Choose if you want to Suggest products customers have recently purchased.
    - If you've selected to not recommend recently purchased products, set the Look back window. This setting specifies the time frame the model considers before recommending the product to the user again. For example, indicate a customer purchases a laptop every two years. This window will look at the purchase history for the last two years, and if they find an item, the item will be filtered from the recommendations.
        ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/step2forproductrecommendation.PNG?raw=true)

    - Select Next to proceed to the next step.
6. Add required data
    - Select **Add data** for Customer transaction history and choose the entity that provides the transaction/purchase history information as described in the prerequisites.
    - Map the semantic fields to attributes within your purchase history entity and select Next. For descriptions of the fields, have a look at the prerequisites.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/step3forproductrecommendation.PNG?raw=true)
    - If the fields aren't filled in, configure the relationship from your purchase history entity to the Customer entity.
        - Select the Purchase history entity.
        - Select the Field that identifies the customer in the purchase history entity. It needs to relate to the primary customer ID of your **Customer entity**.
        - Select the Customer entity that matches your primary customer entity.
        - Enter a name that describes the relationship.
        - Select Save.
        - Select Next.

8. Set update schedule:
    - In the Data update schedule step, choose the frequency to retrain your model based on the latest data. This setting is important to update the accuracy of predictions as new data is ingested in audience insights. Most businesses can retrain once per month and get a good accuracy for their prediction.
    - Select Next.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep8.PNG?raw=true)

9. Review and run the model configuration:
    - Set a frequency to retrain your model. This setting is important to update the accuracy of predictions as new data is imported into Customer Insights. Most businesses can retrain once per month and get a good accuracy for their prediction.
    - Select Next
    - Review the configuration. You can go back to any part of the prediction configuration by selecting Edit under the shown value. Or you can select a configuration step from the progress indicator.
    - If all values are configured correctly, select Save and run to begin the prediction process. On the My predictions tab, you can see the status of your predictions. The process may take several hours to complete depending on the amount of data used in the prediction.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/step4forproductrecommendation.PNG?raw=true)