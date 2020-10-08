Klaviyo Setup Guide
Follow our setup guide to connect Klaviyo to SkyPoint.

Step 01 - Add Dataflow
        Click on Add Dataflow on the right top corner of the screen.
        Enter a Name. (Name starts with a letter and only Letters and Numbers are allowed. No Spcaes)
        Click Next.
        You will be directed to choose a Connector.

Step 02 - Access Source Data 
In order to allow SkyPoint access to your Klaviyo account for data ingest, you'll need the following details:

API Key
Once you enter all the API Key, Click Connect:

This will fetch all List, Campaigns and Metrices.

Upon clicking the Connect button, it will validate your credentials, if it is successful you will see a notification Data loaded successfully else it will show the error that login has failed.

Upon successful connection, it will show the names of all Lists, Campaigns and Metrices imported from the source with headers like Name, Type, Purpose etc.

Obtain API Key from Klaviyo
Perform the following steps to retrieve the API Key:

1. Log in to Klaviyo.
2. Go to Account>>Settings
3. Click on API Key



Step 03 - Action Button.
Action button includes specific actions on the imported lists.

Show All
When you select Show All dropdown, the list will show all the files available in the folder.
Show Selected
Once you click on the Show Selected option, the list will show only the selected files from all of the data in the folder.
Select All
With one click you can Select All the files in that list imported form selceted folder.
Clear All
If you don't want to get all the folders selected, with just one click of the Clear All button all the selections will be removed form the selection.

Step 04 - Save and Run

Select the required enities and click on Save button.

You will be taken to the Dataflow page.

You can Run the data flow as and when required by choosing the Run action from dataflow screen.

Upon successful run two entities will be created named klaviyo_metrices from all Metrices, klaviyo_lists from all Lists and klaviyo_campaigns from all Campaigns.


