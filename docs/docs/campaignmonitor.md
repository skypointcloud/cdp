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
        

1. Click **Connect**
    - Once you click the Connect button you will see a notification *Data loaded successfuly*
    - You will see the list of data imported from the source with headers; **Name**, **Type**, **Entity**.

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


## Import 

We import CM data into two consolidated entities

1. CM-Lists
1. CM-Campaigns 

Export

SkyPoint allows you to export audiences as CM lists for targetted marketing 

Exports to	Name of the audience being exported

Name	Campaign Monitor list

Please note that exporting audiences to multiple Campaign Monitor lists will count against your subscriber limit and may affect your billing.

