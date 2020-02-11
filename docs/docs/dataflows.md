# Data

## Dataflows

1. Click on Ingest. It will take you to PowerBI Login page.

1. Click on Create button on the top bar and select Dataflow

1. Click on Add New Entities.

1. Click on Text/CSV

1. Open a new tab and go to https://portal.azure.com/

1. Select the properties of the file (dataset) residing in the blob storage. Make sure that this blob storage is accessible and there is no access issue. 

1. Copy the Uri and paste it on connection settings input which you get after step 4.

1. Give the name to this dataset (entities) and click on Save & Close.

1. Give the name to the dataflow and save it. You can add more datasets (entities) to this dataflow by clicking on the edit option which appears on the expansion of the three-dot button. Then click on add entities and repeat steps 5 to 8.

1. Go back to SkyPoint CDP app and select Dataflow and click on refresh. You would be able to see the dataflow which you have created in the PowerBI.