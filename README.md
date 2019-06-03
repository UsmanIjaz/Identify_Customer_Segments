## Identifying Customer Segments
In this project, we will apply unsupervised learning techniques to identify segments of the population that form the core 
customer base for a mail-order sales company in Germany. These segments can then be used to direct marketing campaigns 
towards audiences that will have the highest expected rate of returns. 
The data that we will use has been provided by Bertelsmann Arvato Analytics, and represents a real-life data 
science task.

### Dataset
There are four files associated with this project:

- Udacity_AZDIAS_Subset.csv: Demographics data for the general population of Germany; 891211 persons (rows) x 85 features (columns).
- Udacity_CUSTOMERS_Subset.csv: Demographics data for customers of a mail-order company; 191652 persons (rows) x 85 features (columns).
- Data_Dictionary.md: Detailed information file about the features in the provided datasets.
- AZDIAS_Feature_Summary.csv: Summary of feature attributes for demographics data; 85 features (rows) x 4 columns

Each row of the demographics files represents a single person, but also includes information outside of individuals, 
including information about their household, building, and neighborhood. We will use this information to cluster the general 
population into groups with similar demographic properties. Then, we will see how the people in the customers dataset fit 
into those created clusters. The hope here is that certain clusters are over-represented in the customers data, as compared to 
the general population; those over-represented clusters will be assumed to be part of the core userbase. 
This information can then be used for further applications, such as targeting for a marketing campaign.

### Preprocessing
It involves the following steps. 
- Assess Missing Data
  - Convert Missing Value Codes to NaNs
  - Assess Missing Data in Each Column
  - Assess Missing Data in Each Row
- Select and Re-Encode Features
  - For numeric and interval data, these features can be kept without changes.
  - Most of the variables in the dataset are ordinal in nature. While ordinal values may technically be non-linear in spacing, 
  make the simplifying assumption that the ordinal variables can be treated as being interval in nature (that is, kept without any changes).
  - Special handling may be necessary for the remaining two variable types: categorical, and 'mixed'.

### Feature Transformation
- Apply Feature Scaling
- Perform Dimensionality Reduction
- Interpret Principal Components

### Clustering
- Apply Clustering to General Population
- Apply All Steps above to the Customer Data
- Compare Customer Data to Demographics Data¶

### Implementation
Implementation is provided in [this notebook](https://github.com/UsmanIjaz/Identify_Customer_Segments/blob/master/Identify_Customer_Segments.ipynb)
. This notebook also includes a detailed discussion about all the steps mentioned above.

### Results
- I think the company's customer base is universal as the cluster assignment proportions are fairly similar between the two. 
All clusters except cluster 3 have a bit higher proportions for the customer data that suggests the people in those clusters 
to be a target audience for the company. On the other hand, as the proportion of the data in cluster 4 is higher for the general population, it suggests that group of people to be outside of the target demographics.
- Cluster 0 is representing people living further away from the city center with seemingly good neighborhood quality. People are more event oriented and less relegious. They seem to live in the area with 3-5 family homes buildings.
- Cluseter 1 contain people with higher number of cars in their PLZ8 region and live in buildings where the number of households is low. It means more people from this group are living in indenpdent houses. Thesepeople live away from the city center and live in the communities with less population.
- Cluster 2 is representing people with higher number of cars in their PLZ8 region and contrary to the previous cluster, they live in buildings where the number of households is above average/high. They live in a microcell with high number of buildings and low share of 1-2 family homes.
- Cluster 3 represents people who live in buildings where the number of households is above average/high. They live in a microcell with high number of buildings, low share of 1-2 family homes and low business share in the area.
