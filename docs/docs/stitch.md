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

In this approach, user do not need to create any manual rule but the algorithm will itself figure out (based on the semantic labels), whether 2 or more records should be considered a match or not.