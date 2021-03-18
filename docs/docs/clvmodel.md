# Customer Lifetime Value Prediction

Predict potential value (revenue) that individual active customers will bring in to your business through a defined future time period. This feature can help you achieve various goals:
1. Identify high-value customers and process this insight
2. Create strategical customer audiences based on their potential value to run personalized campaigns with targeted sales, marketing, and support efforts
3. Guide product development by focusing on features that increase customer value
4. Optimize sales or marketing strategy and allocate budget more accurately for customer outreach
5. Recognize and reward high-value customers through loyalty or rewards programs

## Prerequisites
Before getting started, reflect what CLV means for your business. Currently, we support transaction-based CLV prediction. The predicted value of a customer is based on history of business transactions. To create the prediction, you need at least Contributor permissions.

Since configuring and running a CLV model doesn't take much time, consider creating several models with varying input preferences and compare model results to see which model scenario best fits your business needs.

## Data Requirements
The following data is required, and where marked optional, recommended for increased model performance. The more data the model can process, the more accurate the prediction will be. Therefore, we encourage you to ingest more customer activity data, if available.
1. Customer Identifier: Unique identifier to match transactions to an individual customer
2. Transaction History: Historical transactions log with below semantic data schema.
    - Transaction ID: Unique identifier of each transaction
    - Transaction date: Date, preferably a time stamp of each transaction
    - Transaction amount: Monetary value (for example, revenue or profit margin) of each transaction
    - Label assigned to returns (optional): Boolean value signifying whether the transaction is a return
    - Product ID (optional): Product ID of product involved in the transaction
3. Additional data (optional), for example
    - Web activities: website visit history, email history
    - Loyalty activities: loyalty reward points accrual and redemption history
    - Customer service log, service call, complaint, or return history
4. Data about customer activities (optional):
    - Activity identifiers to distinguish activities of the same type
    - Customer identifiers to map activities to your customers
    - Activity information containing the name and date of the activity
    - The semantic data schema for activities includes:
        - Primary key: A unique identifier for an activity
        - Timestamp: The date and time of the event identified by the primary key
        - Event (activity name): The name of event you want to use
        - Details (amount or value): Details about the customer activity

## Create a Customer Lifetime Value Prediction
With the stitch process done, we can run the clv prediction.
Below are the necessary steps required to run the prediction.
1. Go to **Insights** > **Predictions** and select to use the Customer Lifetime Value Model.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvstep1.PNG?raw=true)

2. A new pop up will open on the right side of the page.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/popup.PNG?raw=true)

3. Name this model and the Output entity name to distinguish them from other models or entities.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvstep2.PNG?raw=true)

4. Select Next.
5. Define model preferences
    - Set a Prediction time period to define how far into the future you want to predict the CLV. By default, the unit is set as months. You can change it to years to look further in the future.
    - Specify what Active customers mean for your business. Set the time frame in which a customer must have had at least one transaction to be considered active. The model will only predict CLV for active customers.
        - **Let model calculate purchase interval (recommended)**: The model analyzes your data and determines a time period based on historical purchases.
        - **Set interval manually**: If you have a specific business definition of an active customer, choose this option and set the time period accordingly.
    - Define percentile of High-value customer to enable the model to provide results that fit your business definition.
        - **Model calculation (recommended)**: The model analyzes your data and determines what a high value customer might be for your business based on your customers’ transaction history. The model uses a heuristic rule (inspired by the 80/20 rule or pareto principle) to find the proportion of high-value customers. The percentage of customers that contributed to 80% cumulative revenue for your business in the historical period are considered high-value customers. Typically, less than 30-40% customers contribute to 80% cumulative revenue. However, this number might vary depending on your business and industry.
        - **Percent of top active customers**: Define high-value customers for your business as a percentile of top active paying customers. For example, you can use this option to define high-value customers as top 20% of future paying customers.

        ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvstep3.PNG?raw=true)

    - Select Next to proceed to the next step.
6. Add required data
    - In the Required data step, select Add data for Customer transaction history and choose the entity that provides the transaction history information as described in the prerequisites.
    - Map the semantic fields to attributes within your purchase history entity and select Next.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvstep5.PNG?raw=true)

7. Add optional data
    - In the Additional data (optional) step, select Add data. Choose the customer activity entity that provides the customer activity information as described in the prerequisites.
    - Map the semantic fields to attributes within your customer activity entity and select Next.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvstep7.PNG?raw=true)

8. Set update schedule:
    - In the Data update schedule step, choose the frequency to retrain your model based on the latest data. This setting is important to update the accuracy of predictions as new data is ingested in audience insights. Most businesses can retrain once per month and get a good accuracy for their prediction.
    - Select Next.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep8.PNG?raw=true)

9. Review and run the model configuration:
    - In the Review your model details step, validate the configuration of the prediction. You can go back to any part of the prediction configuration by selecting Edit under the shown value. You can also select a configuration step from the progress indicator.
    - If all values are configured correctly, select Save and run to start running the model. On the My predictions tab, you can see the status of the prediction process. The process may take several hours to complete depending on the amount of data used in the prediction.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvstep8.PNG?raw=true)