# Shopify

In order to allow SkyPoint access to your Shopify account, you'll need:

1. **Hostname**
1. **API Key**
1. **Password**

To generate a API key + password combination, follow the [Private Apps](https://shopify.dev/tutorials/authenticate-a-private-app-with-shopify-admin "Shopify Private Apps") instructions on Shopify. 

In order for SkyPoint to import the Shopify customer, products, abandoned checkouts and order details, the permissions read_orders and read_customers must be granted to the generated API key.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/shopify_status.jpg?raw=true)

When we click on **Connect**, we can clearly see the entity details table that contains attributes namely Purpose, Table name, Entity Name with a checkbox option allowing the user to select/de-select a particular purpose based on requirements.

## Purposes

The important thing to notice here is that we provide the functionality to the user to choose what type of action needs to be taken during processing after integration.
For every entity, there are certain purposes desginated to them. Some of them are:
1. CDP 
2. Privacy
3. All

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/purpose.jpg?raw=true)

## Steps to Input data using Shopify Connector

1. Navigate to the platform and go to Data.
2. Create a new dataflow and attach a connector of the category Shopify and fill in all the credentials required.
3. Follow [this](https://skypointcdpdocs.z22.web.core.windows.net/docs/dataflows.html) to get a better understanding of how to input data. This will be beneficial for data processsing as the data will be stored in a convenient manner. 
4. As the data gets integrated, we will be able to see the number of entities present in that dataflow. On successful completion of the process, the status of the dataflow will be a green check denoting that the data has been integrated and can now be taken into further usages.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/dataflow_status.png?raw=true)

5. In entities, we will be able to see the names of the different entities present in the data, the number of records present in each entity, entity type(**default: Custom**) and many more. There are filters present on top of every column which gives user the ability to search a particular entity based on some criteria. By clicking on a particular entity, we can get its details like the **attributes** defining all the different attributes present in the data with their datatypes. To know more about the entities, visit [here](https://skypointcdpdocs.z22.web.core.windows.net/docs/entities.html)

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/entity-dash.jpg?raw=true)

6. Next, based on the requirements, the data can be processed using the Stitch operation offered on our Platform. The data that has been collected in the previous processes is now ready for some mapping. For that, we provide the **Stitch** option that helps the user to map different entities and find correation between entities and create a cumulative entity with maximum information on the data. The Stich involves three different types of actions which helps in refining the data. They are:
    - Map: Mapping involves correlating different entities in a dataflow using specific feature attributes so as to produce a more extractable data-form.
    - Match: After successful completion of Map, we are ready to match the entities. The match phase specifies how to combine your datasets into a cumulative customer profile dataset. 
    - Merge: The final phase of Stitch is Merge where we choose and exclude attributes to merge within or mapped and matched data. Some of the attrbiutes are automatically merged.

To know more about Stitch, click [here](https://skypointcdpdocs.z22.web.core.windows.net/docs/stitch.html)

## Privacy

In Privacy section, the most specific section that determines what all actions can be taken out of the dataset that has been integrated in the previous processes with the user's consent is **PRIVACY CENTER**. The probable 5 actions that can be used to process the data on a CDP. They are:

1. **Download**:  Enabling this feature will let the platform/client download and use the data for anything and everything.
2. **Erase**: Enabling this feature states that if a user removes his/her account from a particular server, all the data associated with that user will be erased.
3. **Consent**: Enabling this feature will let the user consent of all the actions and informed with all the activities performed on his/her data through reports which can be gererated from the [Report](https://skypointcdpdocs.z22.web.core.windows.net/docs/privacyreports.html) Section.
4. **Do not Sell**: Enabling this feature will prohibit the platform from using any user's data out of this domain and hence cannot be sold or shared with other identities.
5. **Update Inaccuracies**: Enabling this feature will help us diagnose error/inaccuracy in a very understandable manner and also update certain settings with respect to improvement.

To know more about setting up the Privacy Center, click [here](https://skypointcdpdocs.z22.web.core.windows.net/docs/privacycenter.html)

## Insights

In this section, we try to produce additional information and insights about the segments of data which we currently have. This section is sub-sectioned into 3 namely:
1. **Profiles**: When the data has been processed, it needs to be profiled. Profiling helps in giving feature insights to individuals whose entry is present in the data and have been summarized with some security. When we navigate to the Profile section of the platform, we can see these profiles made, with entries like first name, last name, etc.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/profiles.jpg?raw=true)

2. **Audiences**: In this section, we can create and oversee the audiences table which is a tabular representation denoting the number of members in every audience created with their current status. An audience is a group of profiles characterized by a defined set of attributes based filters. The other table below it elaborates the work history that corresponds to all the successful and failed iterations over creating audiences.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/audience.jpg?raw=true)

3. **Metrics**:  The key statistics that needs to be represented on the dashboard is evaluated and processsed in this section. Considering the case where the data is filled with entries of user data, the metrics can be total time spent, total number of orders, etc.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/metrics.jpg?raw=true)

## Action

This is the section of our cloud platform that helps us in exporting data to another data storage service so that every ogranization using this platform can store its data in a differentiated manner. Some of the options that our platform offer to export data are:
1. Azure Blob Storage: Azure Blob storage is Microsoft's object storage solution for the cloud. Blob storage is optimized for storing massive amounts of unstructured data, such as text or binary data.
2. Azure Data Lake Gen2: Azure Data Lake Storage Gen2 is a set of capabilities dedicated to big data analytics, built on Azure Blob Storage. Data Lake Storage Gen2 is the result of converging the capabilities of our two existing storage services, Azure Blob storage and Azure Data Lake Storage Gen1.
3. Amazon S3: Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. This means customers of all sizes and industries can use it to store and protect any amount of data for a range of use cases, such as data lakes, websites, mobile applications, backup and restore, archive, enterprise applications, IoT devices, and big data analytics.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/action.png?raw=true)