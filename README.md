# DataCleaningFinalProject
## Group members: Adit Rathi, Himani Mehta, Ashwini Karkhanis

### 1. Use or create an original dataset (meaning that you haven't analyzed the dataset for this class before). Be sure to explain where your dataset comes from and where it can be found (or if you made it, how you made it).
For this project we have opted for the NYC Airbnb dataset. The source of this dataset is Kaggle (https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data). 

### 2. Identify what would make the dataset fit for use.
Dealing with NULL values and outliers will make the dataset more optimum for use. Furthermore, the dataset can be enhanced by adding more categorical variables and lable enconding them. This will give a range of filters during visualization and enable flexible analysis.

### 3. Evaluate if the data are fit for use or if cleaning will need to be done. If cleaning will need to be done, identify the cleaning steps that will be taken.
- After conducting the Exploratory Data Analysis, we found that there are some discripancies with the data and it was not fit for use. 
The first step will be dealing with the null vlaues. There are 4 columns: 'name', 'host_name', 'last_review', and 'reviews_per_month' that have null values. We will drop the 'name' and 'host_name' columns. It is an interesting observation that the number of null values in the 'last_review' and 'reviews_per_month' columns is the same. Further we will determine if both are null for a single record. If this condition is met, then we will be able to conclue that the listing is new and has no previous reviews. Based on this, we will add a categorical column that will indicate of the property is new or old.
- Further, we will deal with outliers. Now the outliers will prevail in columns like location ('latitude' & 'longitude'), 'price' and 'minimum_nights'.
In order to determine if there exist any outliers in the latitude and longitude columns, we will plot each record on the map to ensure if the location of the listings is confined to the state of New York. 
Next, the price of a listing cannot be 0. Hence, for listings with price 0, we will replace it with the average cost of lisitngs in the respective neighbourhood.
For 'minimum_nights', we noticed a few outliers. We decided to calculate the upper quartile (11) and the lower quartile (-5) based on the formula. Based on EDA, the lowest number of nights was 0, which is correct. However, there were anomalies in the upper quartile. As per Airbnb policies, no lisitng can exceed the stay of 90 days. Hence we will replace all the values above 90 with 90. Further, we will added a categorical column based on the minumum number of nights. If it exceeds 28 days, then the lisitng will be a Long-Stay Listing else, it will be a Short-Stay Listing.

### 4. Tools
For this project, we have used Jupyter Notebook. We have used python and libraries like pandas, seaborn, numpy, matplotlib and sklearn.
