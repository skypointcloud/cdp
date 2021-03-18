# Transactional Churn Prediction

## Prerequisites
1. The user must have at least Contributor permissions in our platform in order to create and formulate a transactional churn model.
2. The Stitch Process must be complete.
3. Business knowledge to understand what churn means for your business. We support time-based churn definitions, meaning a profile is considered to have churned after a period of no purchases.
4. Data about your transactions/purchases and their history:
    - Transaction identifiers to distinguish purchases/transactions.
    - profile identifiers to match transactions to your profiles.
    - Transaction event dates, which define the dates the transaction occurred on.
    - The semantic data schema for purchases/transactions requires the following information:
        - **Transaction ID**: A unique identifier of a purchase or transaction.
        - **Transaction Date**: The date of the purchase or transaction.
        - **Value of the transaction**: The currency/numerical value amount of the transaction/item.
        - **(Optional) Unique product ID**: The ID of the product or service purchased if your data is at a line item level.
        - **(Optional) Whether this transaction was a return**: A true/false field that identifies if the transaction was a return or not. If the Value of the transaction is negative, we will also use this information to infer a return.
5. (Optional) Data about profile activities:
    - Activity identifiers to distinguish activities of the same type.
    - profile identifiers to map activities to your profiles.
    - Activity information containing the name and date of the activity.
    - The semantic data schema for profile activities includes:
        - **Primary key**: A unique identifier for an activity. For example, a website visit or a usage record showing the profile tried a sample of your product.
        - **Timestamp**: The date and time of the event identified by the primary key.
        - **Event**: The name of the event you want to use. For example, a field called "UserAction" in a grocery store might be a coupon use by the profile.
        - **Details**: Detailed information about the event. For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.

## Create A Transaction Churn Prediction
With the stitch process done, we can run the Transactional churn prediction.
Below are the necessary steps required to run the prediction.
1. Go to **Insights** > **Predictions** and select to use the Customer Churn Model.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep1.PNG?raw=true)

2. Select the **Transactional** option and select **Get Started**

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep2.PNG?raw=true)

3. Name the model and the output entity.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep3.PNG?raw=true)

4. Define two conditions for the churn model:
    - **Prediction Window :** This setting defines how far into the future do the user want to predict the profile churn. Set a window of days to predict churn for in the Identify profiles who may churn in the next field. For example, predict the risk of churn for your profiles over the next 90 days to align to your marketing retention efforts. Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.
    - **Churn Definition** The duration without purchase after which a profile is considered churned. Enter the number of days to define churn in the A profile has churned if they've made no purchases in: field. For example, if a profile has made no purchases in the last 30 days, they might be considered as churned for your business.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep4.PNG?raw=true)

5. Select **Purchase history(required)** and select **Add Data** for subscription history.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep5.PNG?raw=true)

6. Add the profile entity and map the fields to the corresponding fields required by the model.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep6.PNG?raw=true)

7. You can add any additional data that you mind requiring for the purpose of mapping.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep7.PNG?raw=true)

8. Select Next to set the model schedule. The model needs to train regularly to learn new patterns when there is new data ingested.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep8.PNG?raw=true)

9. After reviewing all the details, select **Save And Run**.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep9.PNG?raw=true)

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
        - **A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for profiles who churned is greater than the baseline rate by at least 10%.
        - **B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for profiles who churned is up to 10% greater than the baseline.
        - **C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for profiles who churned is less than the baseline.
        - Baseline takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less. It uses these fractions to create a business rule for profiles who have not purchased in this time frame. These profiles are considered as churned. The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.

        ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/reviewmodel.PNG?raw=true)

    - Likelihood to churn (number of profiles): Groups of profiles based on their predicted risk of churn. This data can help you later if you want to create an audience of profiles with high churn risk. Such audiences help to understand where your cutoff should be for audience membership.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/likelihood.PNG?raw=true)

    - Most influential factors: There are many factors that are taken into account when creating your prediction. Each of the factors has its importance calculated for the aggregated predictions a model creates. You can use these factors to help validate your prediction results. Or you can use this information later to create audiences that could help influence churn risk for profiles.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/mostinfluencialfactors.PNG?raw=true)