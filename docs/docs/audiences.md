# Audience

**Audiences**

In this section, we can create and oversee the audiences table which is a tabular representation denoting the number of members in every audience created with their current status. An audience is a group of profiles characterized by a defined set of attributes based filters. The other table below it elaborates the work history that corresponds to all the successful and failed iterations over creating audiences. In audiences, we define complex filters around the unified profile entity and its related entities. Each audience, after processing, creates a set of profile records that you can export and take action on. Audiences are managed on the Audiences page.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/audiences.jpg?raw=true)

## Steps to Create Audiences
The following example illustrates the audience of patients having claim status as “pending”. We've defined an audience for patients whose claim status is pending. While creating an audience, you can save a draft. It will be saved as an inactive audience, and can't be activated it finished with a valid configuration.

1. Go to **Insights** >> **Audience**
2. Select **New Audience** >> **Blank Audience**
3. Provide an Output Entity name for the audience. Also, provide a display name and a description that helps identifying the audience.
4. Select **Next** to get to a page where you define a group. A group is a set of profiles.
5. Choose the entity that includes the attribute you want to distribute by.
6. Choose the attribute to distribute by. This attribute can have one of four value types: numerical, string, date, or Boolean.
7. Choose an operator and a value for the selected attribute.
8. To add more conditions to a group, you can use two logical operators:
    - **AND operator**: Both conditions must be met as part of the audienceation process. This option is most useful when you define conditions across different entities
    - **OR operator**: Either one of the conditions needs to be met as part of the audienceation process. This option is most useful when you define multiple conditions for the same entity.
    Note: It's currently possible to nest an OR operator under an AND operator, but not the other way around
9. Each group matches set of profiles. You can combine groups to include the profiles required for your business case
10. Select **Add Group** if you need.
11. Select one of the set operators: Union, Intersect, or Except
    - **Union** unites the two groups
    - **Intersect** overlaps the two groups. Only data that is common to both groups is retained in the unified group
    - **Except** combines the two groups. Only data in group A that is not common to data in group B is retained
12. If the entity is connected to the stitched profile entity through associations, you need to define the association path to create a valid audience. Add the entities from the association path until you can select the Profile:StitchResolvedConflict entity from the dropdown. Then, choose All records for each step
13. By default, audiences generate an output entity that contains all attributes of profile entity which match the defined filters. If an audience is based on other entities than the profile entity, you can add more attributes from these entities to the output entity
14. Select **Save** to save your audience. Your audience will be saved and processed if all requirements are validated. Otherwise, it will be saved as a draft.

**Example** : An audience is based on an entity that contains profile activity data which is related to the profile entity. The audience looks for all profiles that called the help desk in the last 60 days. You can choose to append the call duration and the number of calls to all matching profile records in the output entity. This information might be useful to send an email with helpful links to online help articles and FAQs to profiles who called frequently
**Note** : Every group of an audience should terminate with the Profile entity.