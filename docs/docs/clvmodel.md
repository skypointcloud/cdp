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

## Review prediction results
1. Navigate to **Insights** > **Predictions** tab and select **My Predictions Tab**
2. Select the prediction you want to review results for.
3. There are three primary sections of data within the results page
    - Training model performance: A, B, or C are possible grades. This grade indicates the performance of the prediction and can help you make the decision to use the results stored in the output entity. Select Learn about this score to better understand the underlying model performance metrics and how the final model performance grade was derived. Using the definition of high value customers provided while configuring the prediction, the system assess how the AI model performed in predicting the high value customers as compared to a baseline model. Grades are determined based on the following rules:
        - A when the model accurately predicted at least 5% more high-value customers as compared to the baseline model.
        - B when the model accurately predicted between 0-5% more high-value customers as compared to the baseline model.
        - C when the model accurately predicted fewer high-value customers as compared to the baseline model.
    The Model rating pane shows further details about the AI model performance and the baseline model. The baseline model uses a non-AI based approach to calculate customer lifetime value based primarily on historical purchases made by customers. The standard formula used to calculate CLV by the baseline model:
    ***CLV for each customer = Average monthly purchase made by the customer in the active customer window * Number of months in the CLV prediction period * Overall retention rate of all customers***

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/clvmodelstep9.PNG?raw=true)

    The AI model is compared to the baseline model based on two model performance metrics.
    **Success rate in predicting high-value customers:** See the difference in predicting high-value customers using the AI model compared to the baseline model. For example, 84% success rate means that out of all the high-value customers in the training data, the AI model was able to accurately capture 84%. We then compare this success rate with the success rate of the baseline model to report the relative change. This value is used to assign a grade to the model.
    **Error metrics**: Another metric lets you review the overall performance of the model in terms of error in predicting future values. We use the overall Root Mean Squared Error (RMSE) metric to assess this error. RMSE is a standard way to measure the error of a model in predicting quantitative data. The AI model’s RMSE is compared to the RMSE of the baseline model and the relative difference is reported.
    The AI model prioritizes the accurate ranking of customers according to the value they bring to your business. So only the success rate of predicting high-value customers is used to derive the final model grade. The RMSE metric is sensitive to outliers. In scenarios where you have a small percentage of customers with extraordinarily high purchase values, the overall RMSE metric might not give the full picture of the model performance.
    - Value of customers by percentile: Using your definition of high-value customers, customers are grouped into low-value and high-value, based on their CLV predictions, and shown in a chart. By hovering over the bars in the histogram, you can see the number of customers in each group and the average CLV of that group. This data can help if you want to create segments of customers based on their CLV predictions.
    - Most influential factors: Various factors are considered when creating your CLV prediction based on the input data provided to the AI model. Each of the factors has their importance calculated for the aggregated predictions a model creates. You can use these factors to help validate your prediction results. These factors also provide more insight about the most influential factors that contributed towards predicting CLV across all your customers.