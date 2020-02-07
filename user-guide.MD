# SkyPoint Intelligent Customer Data Platform (ICDP)

SkyPoint Intelligent Customer Data Platform (ICDP) with built-in machine learning, integrates all your data silos (transactional, behavioral, and observational) to unified, 360-degree and real-time customer profiles. Activate unified data and artificial intelligence driven insights for marketing orchestration, personalization, superior customer service, business analytics and GDPR compliance. 

# How Does It Work?

SkyPoint ICDP is a realcdp.org complaint SaaS product. It provides following key capabilities:

- Ingest data from any source
- Capture full detail of ingested data
- Store ingested data indefinitely (subject to privacy constraints)
- Create unified profiles of identified individuals/patients/consumers/provider etc. (360 degree-view)
  - [Common Data Model](https://docs.microsoft.com/common-data-model/) / XDM compliant unified profiles can then be segmented and enriched to create highly flexible targets for marketing or further analysis.
- Share data with any system that needs it (E.g. personalization, seo/sem, marketing, analytics, AI/machine learning etc.)
  - Utilize [Microsoft Power Platform](https://powerplatform.microsoft.com/en-us/) to create automated workflows and no-code solutions.

# Who are the users?

We support 3 security groups natively: Administrator, Contributor and Reader. 

# Getting Started

If you're new to SkyPoint ICDP here's a place to start. You can start collecting data and building segments right out of the box.

# Home 

The first page you see after you login to ICDP app is the home page.

# SkyPoint Cloud Intelligent Customer Data Platform Connector 

This connector is available in the following products and regions:

Service	    Class	    Regions

Flow	      Standard	All Flow  

PowerApps	  Standard	All PowerApps 

US Government (GCC) is not supported. 

Actions

-- GetEntities	
Get entities from a tenant's instance - Use API /api/instances/{instanceId}/manage/dataflows/entities (Retrieves all entities from all dataflows for the provided instanceId).

Return JSON

Name: Name of the entity

Type: Entity type (CDM, System, Custom etc.)

Dataflow: Name of the data flow which the entity was ingested

Created by: By whom was this entity initially created

Created: When was this entity initially created

Updated by: Who last updated the entity's data 

Last updated: Last time this entity's data was updated

Last refreshed: Last time this entity's data was refreshed

-- GetRecord 	
Gets a record (row) from an entity

Input: 

InstanceID, Entity Name, RecordID e.g. GetRecord(GUID, Northwind.Customer, 23)

Output: 

JSON of the row values

-- GetRecords 
Gets records from an entity

Input: 

InstanceID, Entity Name, Total, Skip, Query 

Query is ODATA filter query
Total is total number of rows to retrieve (default is all rows).
Skip is number of rows to skip (default is 0).
Total & Skip can be used for pagination

Output: 

JSON of the rows 

Triggers 

-- GetOnDataFlowRefreshFinished
Triggers a flow when a dataflow refresh is completed

-- GetOnDataFlowRefreshFailed 
Triggers a flow when a dataflow refresh is failed 

# APIs
    
SkyPoint ICDP is an API-First platform. We have provide APIs for all features of the platform. The goal of this section is not to cover all the APIs but to provide a general guidance to help developers to utilize the Swagger tool. 

The details of APIs (including parameters and responses) can be found on the [ICDP Swagger Website](https://sicdpservices.azurewebsites.net/swagger).

## How to use the ICDP Swagger webpage

If you are not familiar with Swagger, see the following step-by-step tutorial: [Swagger UI tutorial](https://idratherbewriting.com/learnapidoc/pubapis_swagger.html).

# Terminology Used in the Application

- Tenant -> You can consider them as clients.

- Instance -> You can consider them as subsidiaries of a single client.

- Dataflows -> It allows you to ingest data from all your sources, transform and load into the data lake in Common Data Model (CDM) schema. You can club common data sources into single dataflow.

- Channels -> They are the visitor touchpoints that you want to monitor with SkyPointCloud.

- Entities -> Individual data sources that are present in the dataflows.

- Stitch -> It consists of 3 steps: Map, Match & Merge. 

  - Map -> It defines the profile data in your entities by choosing the profile attributes, primary key, and types (datatypes defined by SkyPoint Cloud).

  -  Match -> It identifies the unique profiles in your entities by matching records based on certain rules.
 
  - Merge -> It creates an entity of profile records by combining duplicate attributes and removing attributes you don’t need.

- Profiles -> It is generated after the entire stitch process is complete. It contains unified unique records from various entities.

- Timelines -> It shows your customer's timeline in their profiles by defining timeline data in your entities.

- Associations -> It can be used to create associations/relationships between various entities.

- Models -> It integrates your artificial intelligence and machine learning models deployed as web service endpoints to utilizing unified entities (e.g. predictions on unified customer profile and activities). 

- Export -> It exports the entities to a cloud storage account.

- Audiences -> It is a group of profiles characterized by a defined set of attributes based filters. You can schedule audiences to be auto-updated every day or update them manually for onetime use.

- Metrics -> It creates parameters to check the different insights to see if you are on track.

- Orchestrations ->

- Platform -> It consists of notifications, schedule, instance, product, activity stream.

  - Notifications -> It shows the notifications about dataflows and background processes.

  - Schedule -> It allows you to set a schedule to refresh all dataflows and autorun platform processes for the selected instance.

  - Instance -> It displays the various details of the instance such as Tenant Name, Tenant website URL, Tenant identifier, Instance name, Instance identifier, Geographical region, and Timezone.

  - Product -> It allows you to change the language.

  - Activity Stream -> It displays all the activity which was performed in the application.

# User Manual for SkyPoint Cloud ICDP Platform

1. Signup at https://app.skypointcloud.com/signup. It creates 1 Tenant, 1 Sandbox Instance and 1 User.

1. Click on the gearbox on the top right corner to create a new instance.

1. Click on dataflows

   1. Click on Ingest. It will take you to PowerBI Login page.

   1. Click on Create button on the top bar and select Dataflow

   1. Click on Add New Entities.

   1. Click on Text/CSV

   1. Open a new tab and go to https://portal.azure.com/

   1. Select the properties of the file (dataset) residing in the blob storage. Make sure that this blob storage is accessible and there is no access issue. 

   1. Copy the Uri and paste it on connection settings input which you get after step 4.

   1. Give the name to this dataset (entities) and click on Save & Close.

   1. Give the name to the dataflow and save it. You can add more datasets (entities) to this dataflow by clicking on the edit option which appears on the expansion of the three-dot button. Then click on add entities and repeat steps 5 to 8.

   1. Go back to https://app.skypointcloud.com/ and select Dataflow and click on refresh. You would be able to see the dataflow which you have created in the PowerBI.

1. Click on Entities to see individual dataset's data and their attributes. However, you won't be able to see the data for the entities created using PowerBI.

1. Click on Stitch to Map, Match and Merge in order to create a unified dataset with unique records from different entities.

1. Map:

   1. Click on Map.

   1. Select the entities that you want to have in the unified dataset.

   1. Select the appropriate type and primary key.

   1. Click on Save at the top.

1. Match:

   1. Select the entities that you have mapped.

   1. Set the rules in order to match the records from the selected entities.

   1. Click on save.

   1. Click on run.

1. Merge:

   1. Group the attributes which you feel are common across all the entities.

   1. Click on combine attributes.

   1. Click on save.

   1. Click on run.

1. At the end of step 8, you would be able to see 2 new entities in the entities tab. They are MatchedEntity which was created after Match was done successfully and Profile which was created after the Merge was done successfully.

1. Select associations and click on new associations to create one to one, many to one relationships between different entities.

1. Select timelines and click on add timelines.

   1. Select the entity for your timeline.

   1. Select the primary key of that entity.

   1. Select the Timestamp field for which you want the timeline.

   1. Select the event for which you want the timeline.

   1. Select the attribute which defines the title of the event selected in the previous step.

   1. Set up associations between timeline data and corresponding customer entity by selecting the fields with matching data. If the association doesn't exist then it will create a new association (many to one) that you can check in the association tab. No new association is created if there exists an association with the same entities.

1. Select audiences and click on the new audience to create a new audience.

   1. Select the entity which you want to filter.

   1. Select the attribute which you want to filter.

   1. Select the boolean condition.

   1. Input the filter criteria.

   1. Select the entity which is associated with it.

   1. Repeat steps 2 to 4.

   1. Repeat steps 5 to 6.

   1. Add the Profile entity (make sure it is present, else you will get an error).

   1. Repeat steps 2 to 4. 

   1. Click on save.

   1. Click on Back to Audience.

   1. Click on Update Audience.

1. Select metrics and click on add metric.

   1. Select metric type.

   1. Input name and display name.

   1. Click on next.

   1. Select entities.

   1. If you want to add a custom variable select add variable.

      1. Give a name to this variable.

      1. Select the attribute.

      1. Input the expression using this variable.

      1. Click on save.

   1. Select the function.

   1. Choose the entity/variable.

   1. Choose the field.

   1. Click on Save.

   1. Click on back to metrics.

   1. Click on Run.

1. Select profile

   1. Click on customize tile to update what fields you see for each profile.

      1. Click on add to select the attributes you want to see.

      1. Click on add filter to customize the filter list.

      1. Click on save.

      1. Click on back to profiles.

   1. Click on filters to view the filter option.

   1. Click on the profile tile to see the profile summary.

      1. Click on the customer journey to see customer activity.

      1. Click on the metrics to see the KPIs.

      1. Click on all attributes to see all the details of this customer.

1. Click on export to Export the entities to your cloud storage account.

   1. Click on the add export button.
 
   1. Select the storage type.

   1. Input the account name of the storage.

   1. Input the account key of the storage.

   1. Input the container name of the storage.

   1. Input the name for this export.

   1. Click on next.

   1. Select the entities you need to export.

   1. Click on Save.

   1. Click on Export to export it to your cloud storage account.
