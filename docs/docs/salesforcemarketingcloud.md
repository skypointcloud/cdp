
# Salesforce Marketing Cloud Setup Guide

Follow our setup guide to connect **Salesforce Marketing Cloud**  to **SkyPoint**.

You need to provide the following details:

  1. **Client Id**
  1. **Client Secret**
  1. **Authentication URL**
  
  Once you enter all the required details, **Click Connect**: 
  
   * Upon clicking the Connect button, it will validate your credentials, if it is successful you will see a notification **Data loaded successfully** else it will show the error that login has failed.

   * Upon successful connection, it will show the list of data imported from the source with headers, Name, Type, Entity etc.

   * Select the entities you want and save the data flow.

   * You can run the data flow as and when required by choosing the run action from dataflow screen.

### Obtain Client ID and Client Secret from Salesforce Marketing Cloud

Perform the following steps to retrieve the Client ID and Client Secret for a new package:

1.  Log in to Salesforce Marketing Cloud.

2.  Go to **Setup >> Apps >> Installed Packages**

3.  Click **New** to create a new package.

4.  In the New Package Details window, enter the name and description for the package.

    To use OAuth 2.0, select **Create with enhanced functionality (recommended)**.

5.  Click **Add Component**.

6.  Select **API Integration** as the component type.

7.  Click **Next**.

8.  Select **Server-to-Server** as the integration type.

9.  Click **Next**.

10.  Select the following permissions for the Server-to-Server properties:

    -   List and Subscribers - Read, Write

    -   Marketing Cloud Connect - Read, Write

    -   Data Extensions - Read, Write

> These are the minimum permissions required to use Salesforce Marketing Cloud Connector.
> For both import and export integration workflows of SkyPoint and Salesforce Marketing Cloud, client keys will need the following access permissions:    

|Status  |Description  |
|---------|---------|
|Available   |Data source was successfully ingested if a date and time are shown. Or, data source doesn't need to be ingested, if no date and time are shown.          |
|Needs entities   |The data source has no data ingested yet.         |
|Refreshing    |Data ingestion is in progress. You can cancel this operation by selecting **Stop refreshing** in the **Actions** column. Stopping the refresh of a data source will revert it to its last refresh state.       |
|Unable to refresh     |Data ingestion ran into errors. Select the **See details** link to review the errors within 24 hours of the time of failure.         |
    

11.  Click **Save**.

    The Components section displays the Client ID and Client Secret for the package.    

Perform the following steps to retrieve the Client ID and Client Secret for an existing package:

1.  Go to **Setup >> Apps >> Installed Packages**

    

    The Installed Packages page lists all the packages installed in the Salesforce Marketing Cloud account.

    

2.  Select a package and go to the **Components** section.

    

    -   To add a new component, click **Add Component**.

    -   To edit existing component, click **Edit**.

    The Components section displays the Client ID and Client Secret for the package.

3.  Click **Save**.

If an existing package uses OAuth 1.0, you cannot edit the package to use OAuth 2.0. You must create a new package to use OAuth 2.0. SkyPoint recommends that you upgrade to OAuth 2.0 before Salesforce Marketing Cloud drops support for OAuth 1.0.

For information about configuring installed packages and API integration, see the following URL: [https://developer.salesforce.com/docs/atlas.en-us.noversion.mc-app-development.meta/mc-app-development/index.htm](https://developer.salesforce.com/docs/atlas.en-us.noversion.mc-app-development.meta/mc-app-development/index.htm)
Select API Integration as the component type.
