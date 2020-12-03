# SalesForce

In order to allow **SkyPoint** access to your **Salesforce account**, you need to provide the following details:

1. Username
2. Password
3. Security Token
4. Environment URL

## Steps to follow

1. Navigate to **Data** > **Dataflows** and click on *Add Dataflow* button present on top right side of the platform.
2. Fill in the name of the connector and click on **Next**.
3. You will see all the different types of connectors present infront of you. In the search bar present on top right, type Salesforce and select the Salesforce connector.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/salesforceconnect.PNG?raw=true)

4. Next, fill in the display name and type in a breif description about the connector in the ***general section*** and then go to ***Connector Section*** to configure the connector with our platform.
5. Enter all the required details and click on **Connect**. It might take some time to finish up, depending upon the data size.
6. Once its completed, you will be able to see the imported entities below the Connect button.

## The following properties are supported for the Salesforce connector service

1. **Environment URL specify the URL of the Salesforce instance.**

    * Default is "https://login.salesforce.com".

    * To copy data from sandbox, specify "https://test.salesforce.com".

    * To copy data from custom domain, specify, for example, "https://[domain].my.salesforce.com".	


2. **Username specify a username for the user account.**	

3. **Password specify a password for the user account.**

4. **Security Token specify a security token for the user account.**
    * Note : Salesforce account password expires after **every 90 days**, along with that new security token is generated and mailed.

**For instructions on how to get and reset a security token, [Click here](https://help.salesforce.com/articleView?id=user_security_token.htm&type=5).**

**SkyPoint imports Account, Contacts, Leads, Opportunities, all fields including custom fields.**

**Please note that Salesforce rate limits and throttles API calls. API Request Limits and Allocations.**

**To maintain optimum performance and ensure that the Lightning Platform API is available to all our customers, Salesforce balances transaction loads by imposing two types of limits, [Click here](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm)**