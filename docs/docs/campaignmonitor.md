# Campaign Monitor

Dataflow is the first stage of gathering your data from different sources and merge.

## Step 01 - Add Dataflow

- Click on **Add Dataflow** on the right top corner of the screen.
    - Enter a Name. (Name starts with a letter and only **Letters** and **Numbers** are allowed. No Spcaes)
    - Click **Next**.
    - You will be directed to choose a **Connector**.

## Step 02 - Access Source Data
**In order to allow SkyPoint access to your _Campaign Monitor_ account for data ingest, you'll need the following details:**
- **Client ID** (Check with Campaign Monitor source credentials)
- **API Key**
- **Check Boxes**<br>
Select the _Check Box_ if you want initiate the following processes on scheduled runs.
    - [ ] Automatically select new campaign data in scheduled runs.
    - [ ] Automatically select new lists in scheduled runs.
    - Click **Connect**.<br>
    You will see a notification *Data loaded successfuly*.
    - Data from the source will be loaded to the table with headers **Select**, **Name** and **Type**.
        - **Name**<br>
        The file name will be the name of file which exist in the source of **Amazon S3**.
        - **Type**<br>
        **Entity Name** is the unique name that is created for the data collected from the source.

## Step 03 - *Action* Button.
Action button includes specific actions on the imported lists.
- **Show All**<br>
When you select **Show All** dropdown, the list will show all the files available in the folder.
- **Show Selected**<br>
Once you click on the **Show Selected** option, the list will show only the selected files from all of the data in the folder.
- **Select All**<br>
With one click you can **Select All** the files in that list imported form selceted folder.
- **Clear All**<br>
If you don't want to get all the folders selected, with just one click of the **Clear All** button all the selections will be removed form the selection.

## Step 04 - Save
- Click **Save** Button.
    - You will be taken to the Dataflow page.
    
    
- **Action** Button.<br>
Action button includes specific actions on the imported lists.
    - **Show All**<br>
    When you select **Show All** dropdown, the list will show all the files available in the folder.
    - **Show Selected**<br>
    Once you click on the **Show Selected** option, the list will show only the selected files from all of the data in the folder.
    - **Select All**<br>
    With one click you can **Select All** the files in that list imported form selceted folder.
    - **Clear All**<br>
    If you don't want to get all the folders selected, with just one click of the **Clear All** button all the selections will be removed form the selection.


## Do Not Sell Attribute

One of the most important consents that lets the customer believe in the organization with which they are interacting is the DoNotSell feature. Our platform has the feature where the user has the audacity to visit the privacy center of the associated organization and can manage the permissions inclined to his/her personal data. By default, the user's choice is considered False, i.e, the user has not restricted the sharing of his/her data to third party vendours/organizations. To change the consent, the user can go to the privacy portal and can change the consent to True by creating a DSR request. Once the request is made, the user will get an authentication email for confirmation whether the request has been made by the authorized person or not, and post that, the request will be submitted and all of that user's data will be confined and pull out from any other dataflows, if any, other than the parent. 

## Steps to Create a DNS Request

1. Navigate to the privacy center website.
2. Click on **Privacy Actions** and you will be able to see all the different types of requests available for you.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/consents.PNG?raw=true)

3. Click on ***Do Not Sell*** and you will be asked to enter necessary personal details.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/donotsellrequest.PNG?raw=true)

4. Once you have filled all the information, click on **Submit Request** and after a while, you will be sent a link for verification.
5. On complete verification, the status for that particular user will be changed.