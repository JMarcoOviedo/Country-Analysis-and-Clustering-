# Country Analysis and Clustering

Python Version: 3.9 Packages: Pandas, NumPy, Matplotlib, Seaborn, Sklearn, Plotly

* Cleaned and processed the data
* Created Barplots and scatters plots to analyze the data distribution by country and region
* Created a correlation Heat map
* Created a hierarchical clustering map
* Created K-means clusters to discover patterns within the countries 

# Introduction
Using data compiled from the CIA country fact sheet, I will seek insights into similarities between countries with exploratory data analysis and by experimenting with different amounts of clusters.

# Data Analysis and Visualization

<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/country3.png"/>
Looking at the histogram, we can see that most of the countries in this data set have a population of less than 100,000,000. Also, this histogram was limited to countries with a population less than 300,000,000 to give us a better visualization of the distribution.

## 
<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/country1.png"/>
Here we can see the regions with the highest GPD per capita are Western Europe and Northern America. Looking at the standard deviation, which is represented by the black bar, we can see that it is small for countries in Western Europe. This may be because countries in Western Europe tend to have a high GDP per capita. However, looking at the standard deviation for Northern America, we can see that it is very large. This is most likely caused by the United States, which has a much larger GDP per capita when compared to its surrounding countries.

## 
<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/country2.png"/>
Looking at the graph above, we can see that countries with the highest infant mortality rates all have a GDP per capita of less than 10,000. Conversely, countries with a GDP per capita greater than 10,000 all have low infant mortality rates.

## 
<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/country4.png"/>
The literacy rate varies significantly for countries with a GDP per capita below 10,000. For countries with a GDP per capita above 10,000, the literacy rate appears to be above 80%.

<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/country5.png"/>
Looking at the correlation heat map, some of the values that are highly correlated make sense, such as birth rate and infant mortality, as well as population and area. Another interesting observation is the high negative correlation between literacy and birthrate. This may be because countries with higher literacy rates had a greater GDP per capita, with may mean more access to medical services.

##
<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/country6.png"/>
In the hierarchical clustering map, we can see that clusters have formed around certain aspects of a country, such as a cluster of the life and death rates, followed by another cluster of the factors of a country's wealth. Then by climate and geography.

# Data Preparation for K-means

<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/data2.png"/>
This is a count of the null values in our data set. To try to avoid dropping a large percentage of our data set we will look into the countries with missing values. 

<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/data3.png"/>
Looking at the countries, a majority of them are islands, so it makes sense why there might not be a value for agriculture. So instead of dropping these countries, we could set agriculture equal to zero.

<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/data4.png"/>

It appears the Industry and Service columns are also affected by agriculture because their null values also decreased.

Now to fill in the climate and literacy, since there is a region column, we can just take the mean of the climate and literacy in that region and use it to fill in the null values.

<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/data5.png"/>
We still have a few missing values, but we will just drop them since they are now a very small percentage of our overall data set

# K-Means Model

<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/kmeans.png"/>
Looking at the SSD, it appears that after 6 clusters, the difference in SSD doesn't change as much. So we will conduct further visual analysis with the model set to 6 clusters

<img src= "https://github.com/JMarcoOviedo/Country-Analysis-and-Clustering-/blob/main/images/newplot (1).png"/>
It appears the clusters that formed are similar to the region that the country is in, such as a cluster around Northern America, Latin Amer. and Sub-Saharan Africa
