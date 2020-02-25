# Clustering and segmentation of Bengaluru localities based on Resturant style


## Introduction

Bengaluru has become one of the fastest growing cities of India and the world in the recent decade. Owing to the rapid growth of the 
number of software companies that have made Bengaluru their home, it has garnered the title of the Silicon valley of India. The
city in itself has grown to a population over 10 million people. The number of resturants in the city has increased 14 times in the
last 5 years. With resturants serving cuisines of different places around the world, it is truly a cosmopolitan city. 

Nala, a young enterpreneur wants to start a new business in the food and hospitality sector. He wants to open a new resturant that
can cater to the young bangaloreans' needs. The challenge he has, is to **find out in which locality of Bengaluru should he open
his new resturant**. Also, **what are the popular cuisines in Bengaluru?**. Insights into these will help him to open the right type of 
resturant in the right locality to build a growing business.

## Data

To perform the above predictions, we need the data regarding the various resturants and cafes around Bengaluru. Firstly we need data
regarding the various localities of Bengaluru and its latitude and longitude data for using it with Foursquare APIs and also to use it 
with Folium APIs to visualize the data on the map. This data has been handcoded using the online tools to create a dataset of over 
100 Bengaluru localities with their location information.

Foursquare location data provides information on the most visited places in Bengaluru. Using the Foursquare APIs, the data regarding the various resturants
grouped by the localities ( Latitude, Longitude) values are acquired. The Foursquare data also contains resturant details like 
category of the place. We will pre-process the Foursquare location data to fetch all the list of resturants in Bengaluru. 

Along with the Foursquare data, we will also use the Zomato data that provides details of the 
various resturants in Bengaluru along with the cuisine type. The Zomato data can be found here : https://www.kaggle.com/himanshupoddar/zomato-bangalore-restaurants
Combining both of these data will be the dataset on which we will cluster the resturants. 

## Methodology

### Data Collection

The Bengaluru geography data is obtained for the various localities. In total 84 localities of Bengaluru are selected for the study and its geographic data is collected. 

![Bengaluru Geo Data](https://github.com/srikanthkm/Coursera_Capstone/blob/master/images/Bengaluru_geo.png)

### Data Cleansing and Pre-processing

The data related to the restaurants is obtained via the Zomato dataset and preprocessing is performed on it to select only the required features. For each resturant, we extract the Resturant name, category, location and the rating. The rating field is used to filter only the data to include only restaurants with more than 3.5 ( out of 5 ) rating so that the analysis will be more trustworthy.

Any duplicate data of restaurants is also removed from the dataset. 

The cleansed dataset is then merged with the venue data obtained from the Foursquare API. The final dataset contains data about **6160 restaurants across 84 localities**. The study analyzes restaurants across **151 categories**.


**Snapshot of the dataset**   
![Dataset Snapshot](https://github.com/srikanthkm/Coursera_Capstone/blob/master/images/Dataset.png)

### Data Visualization

Next, we try to understand the data by visualize it in the form of charts and dataframe. We try to extract insights about the data using the Pandas operations. 

![Bengaluru Map](https://github.com/srikanthkm/Coursera_Capstone/blob/master/images/Bengaluru_Map.png)

![DistributionByLocality](https://github.com/srikanthkm/Coursera_Capstone/blob/master/images/DataVisualizationByLocality.png)

![DistributionByCategory](https://github.com/srikanthkm/Coursera_Capstone/blob/master/images/DataVisualizationByCategory.png)


### Modeling

The dataset is then processed to extract the top 10 venue category for each of the locality. This helps to generate features for each location to categorize the locality based on the most common category of venues found in a location. 

![OrderedVenues](https://github.com/srikanthkm/Coursera_Capstone/blob/master/images/OrderedVenues.png)


The top 10 venue category for each location is used to cluster the localities into various clusters. 

Based on the above data, K-Means clustering algorithm is applied to segment the localities into various cluster. The optimum Cluster count is calculated to be 5. So, the localities are divided into 5 clusters. 

The dataframe result with the Clusters identified  
![ClusterLabels](https://github.com/srikanthkm/Coursera_Capstone/blob/master/images/ClusterLabels.png)

The color-coded Clusters rendered on a map using Folium.
![Cluster Map](https://github.com/srikanthkm/Coursera_Capstone/blob/master/images/ClustersOnMap1.png)


## Observation & Result

K-Means Clustering algorithm is applied to segment the Bengaluru localities based on the most popular restaurant category available in each of the areas. Cluster labels are assigned to each of the clusters based on segmented data as follow in the rank of number of constituent localities

- Casual Dining
- Quick Bites
- Dessert Parlours
- Cafe
- Clubs. 

The clustering determines that the Casual Dining and Quick Bites are the most popular venue categories in Bengaluru.

Most of the Casual Dining restaurants are concentrated in the city region and the quick bites are spread across the city locations. 
