# Data

## Stitch Overview

The problem in combining customer data with a disparate set of data sources, is that we can rarely find a common, unique key that links all records that belongs to an entity. This is the fundamental reason why identity resolution is required.

Graph-based entity resolution algorithms have emerged as a highly effective approach including utilization of Apache Spark  and GraphFrames. The technique will exhibit an example where efficacy can be achieved based on simple heuristics, and at the same time map a path to a machine-learning assisted entity resolution engine with a powerful knowledge graph at its center.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/stitch.PNG?raw=true)

SkyPoint’s approach to identity resolution produces rich, accurate, and precise customer 360 profiles. There are two phases in the process of building customer 360 profiles.

# Phase I: Data preparation 

All of the initial work needed to get data into a Common Data Model (CDM) environment and prepare it for the matching process.

In this process, we ingest data from multiple sources and then the first phase is to *map* the data columns with their semantic labels. These semantic labels help us to match the data semantically through the more advanced machine learning techniques.

# Phase II: Identity resolution

The records and identities are assigned to unique individuals.

The fundamental task that identity resolution is trying to accomplish is to identify the same individual person within and across all data sources that contain customer information.

There are two approaches that are generally used for this purpose:

## 1. Unique Identifier approach and the Static Rule approach. 

In this approach, user has to manually select the rules based on which the algorithm will be applied. Here user can also select the match precision, for example exact match or high/medium/low.
   1. Exact Match
      - When selecting Exact match, rule will try to match the value exactly. User can also select transformation over the data like, removal of white space. But a values will be considered as match only when they are exactly same after the transformation
   2. Partial/Fuzzy Match
      - When user selects, match precision as High/Medium/low, they gets the option to select which kind of algorithm they want to apply.
      - Currently SkyPoint Supports, Phonetic match, distance based Levenshtein match.
      - User can select Phonetic match over the column in which a match would be considered true when both the matching values are phonetically similar. ex- Dylan and Dillon
      - Distance based Levenshtein is a dynamic programming based approach and one of the most used approach for good quality matches. In the approach, two values are considered to be a match when converting from one value to another, requires less number of transactions. ex- Tony and Tonyy. Converting Tony to Tonyy requires only 1 transactions. Addition of 1 Y. 1 Transaction can be either update, delete, addition  
      - ML based match is also in the work in progress. In this ML based approach, we are creating a statiscal model, which creates a multiple dimentional projection (around 300 dimentional projection) of a value and then we put the locality sensitive hashing to put the similar values in the same bucket. More on this soon...
      - While choosing the desired algorithms, user can apply more than 1 alorithm with logical AND/OR fashion between them to improve their search results
      - Note: The selection of Levenshtein algorithm might increase the Match run time significantly

## 2. Machine Learning approach 

In this approach, we are trying to find the records match without any human involvement. 

In this approach, user do not need to create any manual rule but the algorithm will itself figure out (based on the semantic labels), whether 2 records should be considered a match or not.

## How to use the Stitch process

The stitch process would require three main stages to follow:
1. Map
2. Match
3. Merge

### How to Perform Map

1. Click on Map.

2. Select the entities that you want to have in the unified dataset and click on **Done**.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/map_selectentities.PNG?raw=true)

3. Select the appropriate types for the necessary attributes and primary key.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/map_entities.PNG?raw=true)

4. Click on Save at the top.

5. After saving it, you can run it to complete the mapping stage.

### How to Perform ML Match

1. Select the entities that you have mapped.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/stitch_mlmatch.PNG?raw=true)

2. Set the rules in order to match the records from the selected entities.

3. Set a threshold to formulate a baseline for filtering the match results and refining the best possible identities. Higher the threshold, higher will be the match accuracy with respect to mapped entities.

3. Click on save.

4. Click on run to execute the ML Match stage.

5. If everything works fine, you will be able to see the result on top of your screen. You will get to have a numerical understanding about the unique identities present in your data and the matched and unmatched records.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/mlmatch_result.PNG?raw=true)

**Note** : There is a tabular representation of all the entities considered for matching and their results with a numeric representation of unique records and matched records.

6. For a more visual understanding over the matched records, click on ***View Results***.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/mlmatch_viewresult.PNG?raw=true)

### How to Perform ML Merge

1. Group the attributes which you feel are common across all the entities. There might be different representations of the same data i.e conflicting values of some attributes over all the different datasets used for merge.

2. Click on combine attributes.

3. Click on save.

4. Click on run.