# Shopify

In order to allow SkyPoint access to your Shopify account, you'll need:

1. Hostname
1. API Key
1. Password

To generate a API key + password combination, follow the [Private Apps](https://shopify.dev/tutorials/authenticate-a-private-app-with-shopify-admin "Shopify Private Apps") instructions on Shopify. 

In order for SkyPoint to import the Shopify customer, products, abandoned checkouts and order details the permissions read_orders and read_customers must be granted to the generated API key.

## Steps to Ingest data using Shopify Connector

1. Navigate to the platform and go to Data.
2. Create a new dataflow and attach a connector of the category Shopify and fill in all the credentials required.
3. Follow [this](https://skypointcdpdocs.z22.web.core.windows.net/docs/dataflows.html) to get a better understanding of how to ingest data.
4. As the data gets ingested, we will be able to see the number of entities present in that dataflow.
5. To know more about the entities, visit [here](https://skypointcdpdocs.z22.web.core.windows.net/docs/entities.html)
6. Next, based on the requirements, the datacan be processed using the Stitch operation offered on our Platform. To know more about Stitch, click [here](https://skypointcdpdocs.z22.web.core.windows.net/docs/stitch.html)

### Purposes

The important thing to notice here is that we provide the functionality to the user to choose what type of action needs to be taken during processing after ingestion.
For every entity, there are certain purposes desginated to them. Some of them are:
1. All
2. CDP
3. Privacy