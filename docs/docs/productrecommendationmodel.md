# Product Recommendation Prediction

The product recommendation model creates sets of predictive product recommendations. Recommendations are based on previous purchase behavior and customers with similar purchase patterns. You can create new product recommendation predictions on the Intelligence > Predictions page. Select My predictions to see other predictions that you've created.
Product recommendations may be subject to local laws and regulations and customer expectations, which the model is not built to specifically take into account. As a user of this predictive capability, you must review the recommendations prior to delivering them to your customers to ensure you are complying with any applicable laws or regulations, and customer expectations for what you may recommend.
Additionally, the output of this model will give you recommendations based on the product ID. Your delivery mechanism will need to map the predicted product IDs to appropriate content for your customers to account for localization, image content, and other business-specific content or behavior.

## Prerequisites
1. Business knowledge to understand different types of products for your business and how your customers interact with them. We support recommending products that have been previously purchased by your customers or recommendations for new products.
2. Data about transactions, purchases, and their history:
    - Transaction identifiers to distinguish purchases or transactions.
    - Customer identifiers to map transactions to your customers.
    - Transaction event dates that specify dates the transaction occurred on.
    - (Optional) Product ID information for the transaction.
    - (Optional) Product catalog data entity to use a product filter.
    - (Optional) If a transaction is a return or not.
    - The semantic data schema requires the following information:
        - **Transaction ID**: A unique identifier of a purchase or transaction.
        - **Transaction date**: The date of the purchase or transaction.
        - **Value of the transaction**: The numerical value of the purchase or transaction.
        - **Unique product ID**: The ID of the product or service purchased if your data is at a line item level.
        - **(Optional) Purchase or return**: A true/false field that identifies if the transaction was a return or not. If the Value of the transaction is negative, we will also use this information to infer a return.

## Create a Product Recommendation Model
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

## Review prediction results
1. Navigate to **Insights** > **Predictions** tab and select **My Predictions Tab**
2. Select the prediction you want to review results for.
    - **Prediction name**: The name of the prediction provided when creating it.
    - **Prediction type**: The type of model used for the prediction
    - **Output entity**: Name of the entity to store the output of the prediction. You can find an entity with this name on Data > Entities.
    - **Predicted field**: This field is populated only for some types of predictions, and isn't used in churn prediction.
    - **Status**: The current status of the prediction's run
        - Draft: The prediction is ready for run.
        - Failed: the prediction has failed. Select Logs for more details.
        - Succeeded: the prediction has succeeded. Select View under the vertical ellipses to review the prediction
3. Select the vertical ellipses next to the prediction you want to review results for and select View
4. There are five primary sections of data within the results page:
    - Training model performance: A, B, or C are possible scores. This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.
        - Scores are determined based on the following rules:
            - A The model will be considered A quality if the "Success @ K" metric is at least 10% more the baseline.
            - B The model will be considered B quality if the "Success @ K" metric is 0% to 10% more than the baseline.
            - C The model will be considered C quality if the "Success @ K" metric is less than the baseline.
            - Baseline: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers. The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product. If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline. If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.
            - Success @ K: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions. For example, in a 12-month period, month 12 might be set aside as a validation set of data. If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.
    - Most suggested products (with tally): The top five products that were predicted for your customers.
    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/step5forproductrecommendation.PNG?raw=true)
    - Key recommendation factors: The model uses the customers' transaction history to make product recommendations. It learns patterns based on past purchases and finds similarities between customers and products. These similarities are then utilized to generate product recommendations. The following are the factors that could influence a product recommendation generated by the model.
        - Past transactions: Purchase patterns in the past were utilized by the model to generate product recommendations. For example, the model can recommend a Surface Arc Mouse if someone recently purchased a Surface Book 3 and a Surface Pen. The model learned that historically, many customers had purchased a Surface Arc Mouse after purchasing a Surface Book 3 and a Surface Pen.
        - Customer similarity: A recommended product was historically purchased by other customers who show similar purchase patterns. For example, John was recommended Surface Headphones 2 because Jennifer and Brad recently purchased Surface Headphones 2. The model believes John is similar to Jennifer and Brad because they have historically had similar purchase patterns.
        - Product similarity: A recommended product is similar to other products that the customer had previously purchased. The model considers two products to be similar if they were bought together or by similar customers. For example, someone gets a recommendation for a USB Storage Drive because they previously purchased a USB-C to USB Adapter and the model believes that USB Storage Drive is similar to USB-C to USB Adapter based on historical purchase patterns.