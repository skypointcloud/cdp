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
    
    - Click **Save**.
    - Once you select the **S3 Bucket** you will see a notification *Data loaded successfuly*.
    - Data from the source will be loaded to the table with headers **File Name**, **Entity Name**, **Datetime Format**, **Delimiter**, 
    - **First Row as Header**, **Advacned Settings**.
        - **File Name**<br>
        The file name will be the name of file which exist in the source of **Amazon S3**.
        - **Entity Name**<br>
        **Entity Name** is the unique name that is created for the data collected from the source.
        - **Datetime Format**<br>
        There are a number of **Datatime Format** is available and SkyPoint CDP is set to automatically detect the **Datetime Format**.
        - **Delimiter**<br>
        **Delimiter** is the key that is used for setting up a boundary or a separator of veriables in the data imported. Currently the available seperators are, *Comma (,)*, *Semicolon (;)*, *Pipe (|)*, *Tab (\t)*, *Start of Heading (\u0001)* and *No Delimiter*".
        - **First Row as Header**<br>
        This is a checkbox, which call the first row as Header for the table sheet we are importing. The system will automatically collect the data according to the Header Contents.
        - **Advacned Settings**<br>
        Advanced Settings will allow you to fine tune the import process with minute details.




In order to allow SkyPoint access to your **Campaign Monitor** account, you'll need the following details:
1. Enter the **Client ID** (Check with Campaign Monitor source credentials.)
1. Enter **API Key**
1. There is two chck boxes select it according to your requirements.
    - **Automatically select new campaigns in scheduled runs**.<br>
    Once you schedule the import for future newly created created campaign data will be automatically added to the import queue.
    - **Automatically select new lists in scheduled runs**.<br>
    If you are scheduling any data import, newly created lists will also be added to new ingest queues.
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

