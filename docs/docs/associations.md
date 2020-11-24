# Data

## Associations

This section of our platform lets you create one to one, many to one relationships between different entities by creating an association.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/associations.jpg?raw=true)

## Cardinality
The cardinality of a join between two tables is the numerical relationship between rows of one table and rows in the other. It is very useful for query optimization. They are of four types:
1. One to One – A single row of first table associates with single row of second table.
2. One to Many – A single row of first table associates with more than one rows of second table. 
3. Many to One – Many rows of first table associate with a single row of second table.
4. Many to Many – Many rows of first table associate with many rows of second table.

## Steps to Create An Association

1. Navigate to **Data** > **Associations** and click on *New Association* button present on top of the working area.
2. A new window will pop out from the right side of the screen with some details to fill in.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/newassociation.PNG?raw=true)

3. Fill in the *name of the association* that best describes the relations to be created out of the entities, a brief description about the association, select the source entity, source cardinality target entity and target cardinality.
4. Click on **Save**

**Note** : The user has the ability to edit any relationship previously created.

## Steps to Edit An Association

1. Navigate to **Data** > **Associations** and you will see all the created associations in a tabular form with all their fundamental details.
2. Watch for the association that needs to be modified. Click on the three dot button under Actions and select *Edit*.
3. A new window will pop out from the right side of the screen with all the association's details. Make the changes and click on **Save**.
4. The changes made to the individual association will reflect in the tabular representation as well.