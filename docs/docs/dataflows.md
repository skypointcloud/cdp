# Data

## Dataflows
- Dataflow let you integrate your data from different sources.

### Add Dataflow
1. Click on **Add Dataflow** on the right top corner of the screen.
    - Enter a Name. (Name starts with a letter and only **Letters** and **Numbers** are allowed. No Spcaes)
    - Click **Next**.
    - You will be directed to choose a **Connector**.

### Chosing a Connector
1. Choose a **Connector** listed.
    - You can fiter the list of connectors with respect to the following categories.
      - **All Categories**
      - **Azure**
      - **Database**
      - **File**
      - **Generic Protocol**
      - **NoSQL**
      - **Services and Apps**

### Providing Credentials
1. You will be prompted to enter the following details with respect to the connectors selected.
    - **Amazon S3**
        - **Access key ID** (Check with Amazon S3 source credentials.)
        - **Secret Access Key**
        **S3 Bucket**<br>
        (Select the folder you want download the data from the source)<br>
        Click **Save**<br>
        Once you selcet the S3 Bucket you will see a notification *Data loaded successfuly*
    - **Dynamic365**
        - **Username** (Check with Amazon S3 source credentials.)
        - **password**
        - **clienid**
        - **clientsecret**
        - **domain url**

### Connection
1. Click on Connect

### Saving
1. Click Save

### Run
1. After the connection is established, go to the ellipsis under the column name "action" on the right corner of the dataflow row, click and choose start to ingest all the entities. It might take a few minutes and will ultimately show a green tick under the status column.

### Other Connector Process
Independent method to know more about all other connector process please click [HERE](connectors.md)

