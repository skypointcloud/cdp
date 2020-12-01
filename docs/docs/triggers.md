# Triggers

Triggers are actually what causes a function/flow to run. A trigger defines how a function/flow is invoked taking into consideration the conditions behind it.
For SkyPoint's connector, we have 2 different types of triggers available for the flow. They are:

1. **Endpoint for notifications when a dataflow refresh is completed** : This is a trigger that notifies the user when a dataflow refresh is completed. This trigger helps a lot in automatic updation processes where there is a need for daily updates for dataflow refresh and this feature can automate the process of notifying the user when its done.

2. **Endpoint for notifications when a dataflow refresh is failed** : This is a trigger that notifies the user when a dataflow refresh has failed. This trigger helps a lot in automatic updation processes where there is a need for daily updates for dataflow refresh whether it has worked or not, and this feature can automate the process of notifying the user when its failed.