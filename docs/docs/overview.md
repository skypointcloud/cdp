# Overview

SkyPoint Cloud is a customer data platform that champions privacy and compliance through connected privacy-first customer experiences.

## Terminologies Used in the Application

- Tenants -> You can consider them as clients.

- Instances -> You can consider them as subsidiaries of a single client.

- Dataflows (Integrations - Import) -> It allows you to ingest data from all your sources, transform and load into the data lake in Common Data Model (CDM) schema. You can club common data sources into single dataflow.

- Channels -> They are the visitor touchpoints that you want to monitor with SkyPointCloud.

- Entities -> Individual data sources that are present in the dataflows.

- Stitch -> It consists of 3 steps: Map, Match & Merge. 

  - Map -> It defines the profile data in your entities by choosing the profile attributes, primary key, and types (datatypes defined by SkyPoint Cloud).

  - Match -> It identifies the unique profiles in your entities by matching records based on certain rules.
 
  - Merge -> It creates an entity of profile records by combining duplicate attributes and removing attributes you don’t need.

- Profiles -> It is generated after the entire stitch process is complete. It contains unified unique records from various entities.

- Timelines -> It shows your customer's timeline in their profiles by defining timeline data in your entities.

- Associations -> It can be used to create associations/relationships between various entities.

- Models -> It integrates your artificial intelligence and machine learning models deployed as web service endpoints to utilizing unified entities (e.g. predictions on unified customer profile and activities). 

- Audiences -> It is a group of profiles characterized by a defined set of attributes based filters. You can schedule audiences to be auto-updated every day or update them manually for onetime use.

- Metrics -> It creates parameters to check the different insights to see if you are on track.

- Dataflows (Integrations - Export) -> It exports the entities to several destinations including storage accounts and applications. 

- Platform -> It consists of notifications, schedule, instance, product, activity stream.

  - Notifications -> It shows the notifications about dataflows and background processes.

  - Schedule -> It allows you to set a schedule to refresh all dataflows and autorun platform processes for the selected instance.

  - Instance -> It displays the various details of the instance such as Tenant Name, Tenant website URL, Tenant identifier, Instance name, Instance identifier, Geographical region, and Timezone.

  - Product -> It allows you to change the language.

  - Activity Stream -> It displays all the activity which was performed in the application.
