# Azure Blob Storage

Export lets you to export the cdm files to Azure Blob Storage

## Step 01 - Add export

- Click on **Add export** on the left top corner of the screen.
    - Enter a Name. (Name starts with a letter and only **Letters** and **Numbers** are allowed. No Spcaes)
    - Display name (which displays the name in the UI of the export saved).
    - Type. In the type select Azure Blob.

## Step 02 - Export Source Data
**In order to allow SkyPoint access to your _Azure Blob Storage_ account, you'll need the following details:**
- **Account Name** (Check with Microsoft for Azure Blob Storage credentials.)
- **Account key**
- **Secret Access Key**
- **Container**
- Click **Next** Button.

## Step 03 - Entities to export
Here all the **CDM** data will be available Entity wise.
- Select the entities from the list to be exported
- Click **Save** and then click on three dot button and select **Run**.
    - The export will be started.

## Step 04 - Download Exported Data
The data gets exported in the form of csv file/s that gets stored in the storage account under the specified container with the same name as the export name. To access those files, follow the steps.

- Open Mircosoft Azure Storage Explorer and go the storage account selected in the second step during export.
- Navigate to the selected container and click on it.
- You will see a folder named **export-entity**. Double click to open the folder and you will see the exported csv file/s there.
- Double click on the csv files you want to download and the download will start.