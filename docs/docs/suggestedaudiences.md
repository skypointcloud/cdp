# Suggested Audiences

**Suggested Audiences** : Discover interesting audiences of your customers with the help of an AI model. This machine learning powered feature suggests audiences based on measures or customer attributes. It can help improve your KPIs or better understand the influence of attributes in context of other attributes.

**Note** : The suggested audiences feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR"). Your use of this feature to process data may be subject to GDPR or other laws or regulations. You are responsible for ensuring that your use of SkyPoint Cloud, including this feature, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.

## Suggested audiences to improve your KPIs

As a user of audience insights, you likely have a series of measures created that help track your Key Performance Indicators (KPIs). It's important to understand how certain attributes influence this KPI to create audiences and run a highly targeted campaign.
For example, you track a measure called TotalSpendPerCustomer. As a business, you’d like to see this number grow. Choosing a measure as primary attribute, lets you select the attributes that you want to assess for influence. Let's say membership tier, membership period, and occupation. SkyPoint Cloud can then suggest an audience that tells you who are the biggest influence of that measure. For example, Accountants who are Gold members, and who have been with your business for at least five years are the biggest influencer of TotalSpendPerCustomer. You’ll get an estimated audience size for every suggestion. You can use this information to create campaigns for the targeted audiences.

## Understand what influences a customer attribute

You can choose a customer attribute instead of a measure as the primary attribute. Based on your choice of influencing attributes, the AI model creates a series of suggestions that show how the selected attributes influence the primary attribute.
For example, you choose Rewards Member (Yes/No) as the primary attribute. Tenure, Occupation, and Number of Support Tickets are set as other influencing attributes. The AI model could suggest audiences indicating mostly IT professionals with tenure over two years are rewards members. Another suggestion could highlight that accountants with tenure over one year and fewer than three support tickets are rewards members

## Artificial intelligence usage

Using the primary attribute and influencing attributes, a decision tree algorithm suggests interesting audiences. The suggestions are based on rules or patterns that were picked up by the AI algorithm. Only audiences that significantly differ from the average population are shown as suggestions. The comparison to the average population is based on the selected measure or primary attribute

## Responsible AI

Suggested audiences lets you select attributes to create new audiences and process the data you select. When choosing attributes, including sensitive attributes like race, sexual orientation, or gender, you must ensure that you can and should process that data. You are responsible to comply with any laws applicable to your organization and adhere to your organization’s principles and privacy policies.

## Different results for primary attributes with categorical and numeric values

Audience suggestions are different if you choose a numeric attribute or a categorical attribute as the primary attribute. Values in a categorical attribute contain two or more categories or types. A numeric attribute contains quantitative data and has a sense of measurement associated with it.
With a numeric attribute like annual income or membership period as the primary attribute, the system suggests audiences that have a higher or lower average value of the numeric attribute when compared to all customers.
A categorical attribute like customer satisfaction as the primary attribute results in suggested audiences that have a higher or lower percentage of customers belonging to a particular category when compared to the percentage of all customers belonging to that same category. For example, customer satisfaction is chosen as the primary attribute and it consists of three categories (Low, Medium and High). For each category, audiences will be suggested that have a significantly higher or lower percentage of customers belonging to that category as compared to the proportion of all customers in same category. If 22% of all customers have a High satisfaction, then, only audiences that have a significantly higher or lower proportion of customers with a High satisfaction as compared to 22% will be suggested for that category. Similarly, audiences will be suggested for each of the other categories (Low and Medium) if they are statistically significant.

**Note** : Currently, we only support primary categorical attributes that have up to 10 categories. If you want to see audience suggestions based on a primary attribute with more than 10 categories, we recommend to group some of the categories to reduce the number of categories to 10 or fewer. This limitation only applies to primary attributes. For influencing categorical attributes, we currently support a maximum of 100 categories.

## Limitations

1. Estimated audience size mismatch: If you choose a primary attribute that contains empty values, it can affect the estimated audience size in the audience suggestions. When saving such audience, the actual audience size can be different to the original estimation
2. Boolean type primary attributes don't work: Currently, we only support string and numeric types of data as the primary attribute.
3. Suggested audiences aren't distinct enough: Keep in mind that the selected attributes and the distribution of values of those attributes influences the results. You can change your influencing attributes or even your primary attribute to get different results