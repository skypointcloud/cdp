# Power Platform Connector

## Overview

Power Platform Connector is a wrapper around the API of SkyPoint Cloud that allows the services to interact with the Power Automate and click a custom flow based on actions and triggers. It provides a way for the users to connect and interact with these segments and to build dataflows and many other automated flow based functionality.

## Actions

Actions are the parts of the flow that needs to be run in a systematic manner. They include operations that can help in attaining a list of tables from an instance or maybe it can produce a dynamic response based on requirement during creation of automatic flow.
Skypoint's Power Platform Connector provides three fundamental actions. They are :

1. **Get Entities** : This operation gets entities from an instance. It returns a list of tables present in that instance.

2. **Get Item** : This operation gets an item from an entity. The output of this operation is dynamic and it entirely depends on the entity and the item that need to be extracted.

3. **Get Items From An Entity** : This operation gets items from an entity. The output of this operation is also dynamic and it entirely depends on the entity and the number of items present in that entity.