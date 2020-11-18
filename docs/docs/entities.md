# Data

## Entities

An entity is a collection of attributes and metadata that defines a concept (such as Account or Contact) and can be defined by any data producer. An entity may match the schema of a standard entity, defined as part of the Common Data Model and listed in the [GitHub repository](https://aka.ms/cdmrepo). Entities that don’t match one of the standard shapes are said to be custom entities. All entities in the data lake ingested through dataflows of this instance are visible in this section.

After complete success over the connection establishment and the data ingestion, you will be able to see the different entities that were ingested from the dataflow. They are distinctively shown in a tabular format with some important attributes as names, total records, Source, last refresh date and entity type (by default is CUSTOM).

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/entities.jpg?raw=true)

There are some entries made when entities get imported. They are:
1. **Name** : The name of the entity imported.
2. **Total records** : The cardinality(*number of rows*) of that individual entity.
3. **Source** : The connector through which the entities have been imported.
4. **Last Refresh Date** : The date and time when the entity was last modified.
5. **Entity Type** : The default entity type is *Custom*. When the data entities gets imported from dataflow, the entity type is Custom. On further processing of data, the type changes from custom to Map, Audience, metric depending upon the process done on that entity.
6. **Created By** : The user who created that particular entity.
7. **Edited By** : The user who modified the imported entities to formulate a processed one.
8. **Created Date** : The date and time when the entity was created.
9. **Edited Date** : The date and time when the entity was modified.

## How to Select An Entity

To know more about the data and the attributes of an entity, click on the name of the entity and another screen will be visible with 2 sub-sections describing the attributes of the entity and the data present in it.

## Purpose of Attributes Sub-section

In the Attributes section, you will see a tabular representation of all the attributes present inside that entity with their details such as their datatypes. To handle entities we need to have a proper understanding regarding the type of value that is being processesd.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/attributes.PNG?raw=true)

## Purpose of Data Sub-section

In the data section, we will see a tabular representation of the data with its values with dignified rows and columns. The main purpose of this sub-section is to get a glance over the data and to know what kind of data is to be processed.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/data-entity.jpg?raw=true)

A feature to download the particular entity data in a csv format, is also available at the top right corner on the screen.