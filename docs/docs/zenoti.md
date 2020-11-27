# Zenoti

In order to allow SkyPoint access to your Zenoti account, you'll need:

1. **API Key**
2. **URL**

To know about Zenoti and ways to interact with the API, click [here](https://docs.zenoti.com/#:~:text=You%20can%20get%20your%20key%20from%20Admin%20%3E%20Setup%20%3E%20API%20section)

## Steps to Import Data Using Zenoti Connector

1. Navigate to **Data** > **Dataflows** and click on *Add Dataflow* button present on top right side of the platform.
2. Fill in the name of the connector and click on **Next**.
3. You will see all the different types of connectors present infront of you. In the search bar present on top right, type Zenoti and select the Zenoti connector.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/zenoti_connector.PNG?raw=true)

4. Next, fill in the display name and type in a breif description about the connector in the ***general section*** and then go to ***Connector Section*** to configure the connector with our platform.
5. Enter the API key and the URL and click on **Connect**. It might take some time to finish up, depending upon the data size.
6. Once its completed, you will be able to see the imported entities below the Connect button.
7. Follow [this](https://skypointcdpdocs.z22.web.core.windows.net/docs/dataflows.html) to get a better understanding of how to input data. This will be beneficial for data processsing as the data will be stored in a convenient manner. 
8. As the data gets integrated, we will be able to see the number of entities present in that dataflow. On successful completion of the process, the status of the dataflow will be a green check denoting that the data has been integrated and can now be taken into further usages.

9. In entities, we will be able to see the names of the different entities present in the data, the number of records present in each entity, entity type(**default: Custom**) and many more. There are filters present on top of every column which gives user the ability to search a particular entity based on some criteria. By clicking on a particular entity, we can get its details like the **attributes** defining all the different attributes present in the data with their datatypes. To know more about the entities, visit [here](https://skypointcdpdocs.z22.web.core.windows.net/docs/entities.html)

10. Next, based on the requirements, the data can be processed using the Stitch operation offered on our Platform. The data that has been collected in the previous processes is now ready for some mapping. For that, we provide the **Stitch** option that helps the user to map different entities and find correation between entities and create a cumulative entity with maximum information on the data. The Stich involves three different types of actions which helps in refining the data. They are:
    - Map: Mapping involves correlating different entities in a dataflow using specific feature attributes so as to produce a more extractable data-form.
    - Match: After successful completion of Map, we are ready to match the entities. The match phase specifies how to combine your datasets into a cumulative customer profile dataset. 
    - Merge: The final phase of Stitch is Merge where we choose and exclude attributes to merge within or mapped and matched data. Some of the attrbiutes are automatically merged.

To know more about Stitch, click [here](https://skypointcdpdocs.z22.web.core.windows.net/docs/stitch.html)