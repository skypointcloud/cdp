# Overview

SkyPoint Cloud is a customer data platform that champions privacy and compliance through connected privacy-first customer experiences.

## Terminologies Used in the Application

- **Tenants** : You can consider them as clients. 

- **Instances** : You can consider them as subsidiaries of a single client. As soon as you create an account on our platform, a default instance is created for you namely *Sandbox*.

- **Dataflows (Integrations - Import)** : It allows you to ingest data from all your sources, transform and load into the data lake in Common Data Model (CDM) schema. You can club common data sources into single dataflow.

- **Channels** : They are the visitor touchpoints that you want to monitor with SkyPointCloud.

- **Entities** : Individual data sources that are present in the dataflows.

- **Stitch** : Data Processing is performed in this section. It consists of 3 sub-sections: Map, Match & Merge. 

  - *Map* : It defines the profile data in your entities by choosing the profile attributes, primary key, and types (datatypes defined by SkyPoint Cloud).

  - *Match* : It identifies the unique profiles in your entities by matching records based on certain rules.
 
  - *Merge* : It creates an entity of profile records by combining duplicate attributes and removing attributes you don’t need.

- **Timelines** : It shows your customer's timeline in their profiles by defining timeline data in your entities.

- **Associations** : It can be used to create associations/relationships between various entities.

- **Models** : It integrates your artificial intelligence and machine learning models deployed as web service endpoints to utilizing unified entities (e.g. predictions on unified customer profile and activities). 

- **Profiles** : It is generated after the entire stitch process is complete. It contains unified unique records from various entities.

- **Audiences** : It is a group of profiles characterized by a defined set of attributes based filters. You can schedule audiences to be auto-updated every day or update them manually for onetime use.

- **Metrics** : It creates parameters to check the different insights to see if you are on track.

- **Data Maps** : Mapping different entities in a meaningful manner to formulate a consolidated aspect over the data. It also provides an easier and powerful way to process, manage and secure the data with minimal complexity.

- **Data Subject Requests** : This allows the customer to create a new DSR and shows the DSRs that are currently in review.

- **Dataflows (Integrations - Export)** : It exports the entities to several destinations including storage accounts and applications. 

- **Platform** : It consists of notifications, schedule, instance, product, activity stream.

  - *Tenant* : It displays all the basic details of the tenant with all the services assigned to it.

  - *Instance* : It displays the various details of the instance such as Tenant Name, Tenant website URL, Tenant identifier, Instance name, Instance identifier.

  - *Notifications* : It shows the notifications about dataflows and background processes. This sub-section helps to cover the area where we need to check the status  of an iteration.

  - *Schedule* : It allows you to set a schedule to refresh all dataflows and autorun platform processes for the selected instance.

  - *Activity Stream* : It displays all the activity which was performed in the application.

There are many more processing and security based sections that needs to be covered and hence are covered in their respective sections of the documentation.