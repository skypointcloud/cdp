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
Total is total number of rows to retrieve (default = all rows).
Total is number of rows to skip (default = 0).
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
