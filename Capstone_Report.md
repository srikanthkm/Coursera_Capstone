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
