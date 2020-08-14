# SalesForce

In order to allow **SkyPoint** access to your **Salesforce account**, you need to provide the following details:

  1. **Username**
  1. **Password**
  1. **Security Token**
  1. **Environment URL**
  
  Once you enter all the required details, **Click Connect**: 
  
   * Upon clicking the Connect button, it will validate your credentials, if it is successful you will see a notification **Data loaded successfully** else it will show the error that login has failed.

   * Upon successful connection, it will show the list of data imported from the source with headers, Name, Type, Entity etc.

   * Select the entities you want and save the data flow.

   * You can run the data flow as and when required by choosing the run action from dataflow screen.
        

**The following properties are supported for the Salesforce connector service.**

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
