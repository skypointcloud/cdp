# Amazon S3
In order to allow SkyPoint access to your **Amazon S3** account, you'll need the following details:
1. **Access key ID** (Check with Amazon S3 source credentials.)
1. **Secret Access Key**
1. **S3 Bucket**
    - Select the folder you want download the data from the source.
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
        - **Advacned Settings**
- **Advanced Settings**
    <br>When you click on the **Advanced Settings** link, you will see a pop-up window with certain additional information. All these informations are key factors of the source data and how it is organized. If you are getting any errors, please check with the data source for these additional information.
    - **Compression Type**<br>
    Compression type in **Advanced Settings** is the method that is used for compressing the details from the source, Amazon S3. (To identify what is the compression methods that's used, please check with your credentials.)
    - **Row Delimiter**<br>
    The data stream will have a seperator that identify the boundaries of it's flow. If there were any different separator is used in it, that information need to be changed to get more accuracy in data ingestion.
    - **Encoding**<br>
    Since the data is coming in data stream there is always a kind of encoding used for decyphering it. If any seperate value of mentioned in the encoding process, you may need to select the appropriate encoding. Default encoding is **UTF-8**.
    - **Escape Character**<br>
    An escape character is a particular case of metacharacters. Which given an identification of sequence start or end. You can manually select the **Escape Character** from the dropdown.
        - \"/" **Forward Slash**
        - "\\" **Backshlash**
        - **No Escape Character**
    - **Quote Character**<br>
    There are three **Quote Character** types are mentioned in the advanced **Quote Character** dropdown.
        - (") **Double Quote**
        - (') **Single Quote**
        - **No Quote Character**
- 
      
    

