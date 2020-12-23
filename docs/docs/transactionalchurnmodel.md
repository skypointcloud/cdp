# Transactional Churn Prediction

## Prerequisites
1. The user must have at least Contributor permissions in our platform in order to create and formulate a transactional churn model.
2. The Stitch Process must be complete.

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
    - **Prediction Window :** This setting defines how far into the future do the user want to predict the customer churn.
    - **Churn Definition** The duration without purchase after which a customer is considered churned.

    ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep4.PNG?raw=true)

5. Select **Purchase history(required)** and select **Add Data** for subscription history.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep5.PNG?raw=true)

6. Add the customer entity and map the fields to the corresponding fields required by the model.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep6.PNG?raw=true)

7. You can add any additional data that you mind requiring for the purpose of mapping.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep7.PNG?raw=true)

8. Select Next to set the model schedule. The model needs to train regularly to learn new patterns when there is new data ingested.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep8.PNG?raw=true)

9. After reviewing all the details, select **Save And Run**.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/churnmodelstep9.PNG?raw=true)