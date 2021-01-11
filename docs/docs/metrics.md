# Insights

**Metrics**:  The key statistics that needs to be represented on the dashboard is evaluated and processsed in this section. Considering the case where the data is filled with entries of user data, the metrics can be total time spent, total number of orders, etc. Metrics represent the performance indicators that reflect the performance and health of specific business areas. Audience provides an intuitive experience for building different types of metrics, using a query builder, that doesn't require you to code or check your metrics manually. You can track your business metrics on the **Home Page**, see metrics for some specific customers on the Customer Card, and use metrics to define profile metrics on the metrics page.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/metrics.jpg?raw=true)

## Steps to Create Metrics

1. Navigate to **Insights** > **Metrics** and click on **New Metric**.

1. Select the metric type, name and the display name and click on Next. Now, there are three types of metrics offered on the platform.
    1. **Profile Attribute** : A single field per profile that reflects a score, value or state for the profile. Profile attributes are created as attributes in a new system-generated entity called **Profile_Metrics**.
    1. **Profile Metric** : Insights on profle behavior with breakdown by selected dimensions. A new entity is generated for each metric, potentially with multiple records per profile.
    1. **Business Metric** : Tracks your business performace and health of the business. Business metrics can have two different outputs: a numeric output that shows on the **Home Page** or a new entity that you find on the **Entities** page.

1. In the entities section, select the first entity from the drop-down. At this point you should decide whether additional entities are needed as a part of your metrics. To add more entities, select **Add entity** and select entities you want to use for the metric.

1. Optionally, you can configure variables. In the **Variables** section, select **New Variable**. Variables are calculations that are made on each of your selected records. For example, summing point-of-scale(POS) and online sales for each of your profiles' records.

1. Provide a name for the variable.

1. In the expression area, choose a field to begin your calculations with.

1. Type an expression in the expression area while choosing more fields to be included in your calculation.

**Note** : Currently, only arithmetic expressions are supported.

1. In the metric definition section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.

1. Select New Dimension. You can think of a dimension as a group by function. The data output of your metric entity or attribute will be grouped by all of your defined dimensions.

1. Select or enter the following information as part of your dimension's definition.
    1. Entity: If you define a Metric entity, it should include at least one attribute. If you define a Metric attribute, it will include only one attribute by default. This selection is about choosing the entity that includes that attribute.
    1. Field: Choose the specific attribute to be included either in your Metric entity or attribute.
    1. Bucket: Choose whether you want to aggregate data on a daily, monthly, or annual basis. It's a required selection only if you've selected a Date type attribute.
    1. As: Defines the name of your new field.
    1. Display name: Defines the display name of your field.

1. Optionally, add aggregation functions. Any aggregation that you create results in a new value within your Metric entity or attribute. Supported aggregation functions are: Min, Max, Average, Median, Sum, Count Unique, First (takes the first record of a dimension value), and Last (takes the last record added to a dimension value).

1. Select Save to apply your changes to the metric.

1. Click on Run.