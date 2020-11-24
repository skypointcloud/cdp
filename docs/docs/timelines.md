# Data

## Timelines
In this section, we show timeline in the different profiles by defining timeline data in your entities. The first half of the section contains a tabular representation of all the created timelines with their information.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/timelines.jpg?raw=true)

Some of them are:
1. Entity : Corresponds to the entity name that is being used here in the timeline.
2. Source : The connector from which the data was imported.
3. Primary Key : The uniquely identifiable attribute.
4. Status : The status of the run command on timeline.

The second half of this section contains a tabular representation of the history regarding all the actions performed in this section.

## Steps to create a Timeline

1. Navigate to **Data** > **Timelines** and click on *Add timeline*.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/createtimelines.PNG?raw=true)

2. Select the entity for your timeline.
3. Select the primary key of that entity.
4. Select the Timestamp field for which you want the timeline.
5. Select the event for which you want the timeline.
6. Select the attribute which defines the title of the event selected in the previous step.
7. Set up associations between timeline data and corresponding customer entity by selecting the fields with matching data. If the association doesn't exist then it will create a new association (many to one) that you can check in the association tab. No new association is created if there exists an association with the same entities.