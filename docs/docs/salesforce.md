In order to allow SkyPoint access to your Salesforce account, you need to provide the following details:

  1. Username
  2. Password
  3. Security Token
  4. Environment URL
  
  After entering all the required details, Click Connect: 
  
•	Once you click the Connect button, it will validate your credentials, if it is successful you will see a notification Data loaded successfully else it will show error that login has failed.

•	 Upon successful connection, it will show the list of data imported from the source with headers, Name, Type, Entity.

•	Select the entities you want and save the data flow.

•	You can run the data flow as and when required by choosing the run action from dataflow screen.
        

The following properties are supported for the Salesforce connector service.

Environment URL specify the URL of the Salesforce instance.
•	Default is "https://login.salesforce.com".
•	To copy data from sandbox, specify "https://test.salesforce.com".
•	To copy data from custom domain, specify, for example, "https://[domain].my.salesforce.com".	

Username specify a username for the user account.	

Password specify a password for the user account.

Security Token specify a security token for the user account.

For instructions on how to get and reset a security token, see link below. 

https://help.salesforce.com/articleView?id=user_security_token.htm&type=5

SkyPoint imports Account, Contacts, Leads, Opportunities, all fields including custom fields. 

Please note that Salesforce rate limits and throttles API calls. API Request Limits and Allocations

To maintain optimum performance and ensure that the Lightning Platform API is available to all our customers, Salesforce balances transaction loads by imposing two types of limits.

https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm
