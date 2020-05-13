The following properties are supported for the Salesforce connector service.

EnvironmentUrl	Specify the URL of the Salesforce instance.

- Default is "https://login.salesforce.com".
- To copy data from sandbox, specify "https://test.salesforce.com".
- To copy data from custom domain, specify, for example, "https://[domain].my.salesforce.com".	

Username	Specify a user name for the user account.	

Password	Specify a password for the user account.

securityToken	Specify a security token for the user account.

For instructions on how to get and reset a security token, see link below. 

https://help.salesforce.com/articleView?id=user_security_token.htm&type=5

SkyPoint imports Account, Contacts, Leads, Opportunities, all fields including custom fields. 

Please note that Salesforce rate limits and throttles API calls. API Request Limits and Allocations

To maintain optimum performance and ensure that the Lightning Platform API is available to all our customers, Salesforce balances transaction loads by imposing two types of limits.

https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm
