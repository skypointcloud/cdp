# Subscription Churn Prediction

## Prerequisites
1. The user must have at least Contributor permissions in our platform in order to create and formulate a subscription churn model.
2. The Stitch Process must be complete.
3. Business knowledge to understand what churn means for your business. We support time-based churn definitions, meaning a profile is considered to have churned a period of time after their subscription is ended.
4. Data about your subscriptions and their history:
    - Subscription identifiers to distinguish subscriptions.
    - profile identifiers to match subscriptions to your profiles.
    - Subscription event dates, which define start dates, end dates, and the dates the subscription events occurred on.
    - Subscription information to define if it's a recurring subscription and how often it renews.
    - The semantic data schema for subscriptions requires the following information:
        - Subscription ID: A unique identifier of a subscription.
        - Subscription End Date: The date the subscription expires for the profile.
        - Transaction Date: The date a subscription change happened. For example, a profile buying or canceling a subscription.
        - Subscription Start Date: The date the subscription starts for the profile.
        - Is it a recurring subscription: A boolean true/false field that determines if the subscription will renew with the same subscription ID without profile intervention
        - Recurrence Frequency (in months): For recurring subscriptions, it's the period the subscription will renew for. It's represented in months. For example, a yearly subscription that automatically renews for a profile every year for another year has the value 12.
        - (Optional) Subscription Amount: The amount of currency a profile pays for the subscription renewal. It can help identify patterns for different levels of subscriptions.
5. Data about profile activities:
    - Activity identifiers to distinguish activities of the same type.
    - profile identifiers to map activities to your profiles.
    - Activity information containing the name and date of the activity.
    - The semantic data schema for profile activities includes:
        - **Primary key**: A unique identifier for an activity. For example, a website visit or a usage record showing the profile viewed a TV show episode.
        - **Timestamp**: The date and time of the event identified by the primary key.
        - **Event**: The name of the event you want to use. For example, a field called "UserAction" in a streaming video service could have the value of "Viewed".
        - **Details**: Detailed information about the event. For example, a field called "ShowTitle" in a streaming video service could have the value of a video a profile watched.

## Create A Subscription Churn Prediction
With the stitch process done, we can run the subscription churn prediction.
Below are the necessary steps required to run the prediction.
1. Go to **Insights** > **Predictions** and select to use the Customer Churn Model.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep1.PNG?raw=true)

2. Select the **subscription** option and select **Get Started**

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/subscriptionchurnstep1.PNG?raw=true)

3. Name the model and the output entity.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/subscriptionchurnstep2.PNG?raw=true)

4. Define two conditions for the churn model:
    - Enter the number of **Days since subscription ended** that your business considers a customer to be in a churned state. This period is typically liked to business activities like offers or other marketing efforts trying to prevent losing the customer.
    - Enter the number of **Days to look into future to predict churn** to set a window to predict churn for. For example, to predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts. Predicting churn risk for longer or shorter periods of time can make it more difficult to address the factors in your churn risk profile, but this is highly dependent on your specific business requirements. Select Next to continue

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/subscriptionchurnstep3.PNG?raw=true)

5. Select **Subscription history(required)** and select **Add Data** for subscription history.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/subscriptionchurnstep4.PNG?raw=true)

6. Add the subscription history data entity and map the fields to the corresponding fields required by the model.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/subscriptionchurnstep5.PNG?raw=true)

7. Add the customer activity data entity and map the fields to the corresponding fields required by the model.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/subscriptionchurnstep6.PNG?raw=true)

8. Select Next to set the model schedule. The model needs to train regularly to learn new patterns when there is new data ingested.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep8.PNG?raw=true)

9. After reviewing all the details, select **Save And Run**.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/subscriptionchurnstep7.PNG?raw=true)

10. When the model is completely run, you will be able to see your model in the **My Predictions** section. Post completion, an entity will also be created with type **Intelligence** containing the predictions.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/modelcreated.PNG?raw=true)

## Review A Prediction Status And Results
1. Navigate to **Insights** >> **Predictions** and go to **My Predictions**.
2. Select the prediction you want to review.
    - **Prediction name**: Name of the prediction provided when creating it.
    - **Prediction type**: Type of model used for the prediction
    - **Output entity**: Name of the entity to store the output of the prediction. You can find an entity with this name on **Data** > **Entities**.
    - **Predicted field**: This field is populated only for some types of predictions, and isn't used in churn prediction.
    - **Edited**: The date the configuration for the prediction was changed.
3. Select the vertical ellipses just under action column, to review results for the prediction you want to and select View.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/reviewmodel.png?raw=true)

4. There are three primary sections of data within the results page:
    - Training model performance: A, B, or C are possible scores. This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity. Scores are determined based on the following rules:
        - **A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for profile who churned is greater than the historical average churn rate by at least 10% of the historical average churn rate.
        - **B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for profile who churned is up to 10% greater than the historical average churn rate of the historical average churn rate.
        - **C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for profile who churned is less than the historical average churn rate.

        ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/result.PNG?raw=true)

    - Likelihood to churn (number of profile): Groups of profile based on their predicted risk of churn. This data can help you later if you want to create a audience of profile with high churn risk. Such audiences help to understand where your cutoff should be for audience membership.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/likelihood.PNG?raw=true)

    - Most influential factors: There are many factors that are taken into account when creating your prediction. Each of the factors has their importance calculated for the aggregated predictions a model creates. You can use these factors to help validate your prediction results. Or you can use this information later to create audiences that could help influence churn risk for profile.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/mostinfluencialfactorssubscription.PNG?raw=true)