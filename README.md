# Best Suburb to Open a Restaurant in Canberra

## Table of Contents
1. [Introduction](#introduction)
2. [Data](#data)
3. [Methodology](#methodology)
4. [Results](#results)
5. [Discussion](#discussion)
6. [Conclusion](#conclusion)

## Introduction
This is a guide for someone who is interested in opening a restaurant in Canberra. There are a lot of factors that are important for opening and running a successful restaurant. The most important one of them is location. 

Location is the key and it is as important as menu and concept of a restaurant. First of all, we have to decide that which part of the city do we want to open our restaurant. Beside the location there are a couple of other factors to be considered. such as how much is the population of the chosen area and what is the income of the people who live there. Based on these two considerations we can also decide on the theme and price of the restaurant.

Also, there are places that may not have a big population of habitants but if it's a business center it can make a big difference. For example, places like city center (like Civic) or the centers of entertainment (like Manuka) have always a chance even though a lot of other restaurants may exist in those areas. 

Another consideration is that if we want to open a pie shop, we may prefer not to open it in an area that another ten pie shops exist.

As you see it is very important that to do a lot of researches before opening a restaurant to avoid losing money. In this project we try to find the best places in Canberra for opening a successful restaurant.

## Data

For this project, the following factors have to be extracted from various data sources:

-	Percentage of the Australian Capital Territory population for each suburb (Canberra Census)
- Median weekly personal income (Canberra Census)
-	Number of Restaurants in Each Neighborhood (Foursquare API)
- Districs and suburbs of ACT and their coordinates
The Canberra Census data was extracted from: https://en.wikipedia.org

There were not a lot of gathered information about all above data so I just scraped them from multiple sources and were combined them into one final table.

There were some missing data which I used the median for it. For example, there were suburbs that their habitants were very low compared with the other suburbs and there was no clear information about the percentage of population and individual weekly income. I calculated the percentage of population myself considering their number of habitants. Also, for the calculating the missing income I noticed that all suburbs expect one (south Canberra) have very similar income. Therefore, I used the median of more seen income to calculate the weekly individual income.

## Methodology

My final dataset has the main components postcodes, districs, suburbs, Latitude, Longitude, Median weekly personal income(A$) and	Percentage of the ACT population.

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figure1.jpg "Figure 1: Canberra dataset.")

**Figure 1:** Canberra dataset.

The next step was to visualize the location of the various postal codes within Canberra to obtain a general understanding of the location (Figure 2). 

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/Figure2.jpg "Figure 2: Location of each postal code within Canberra, Australia.")

**Figure 2:** Location of each postal code within Canberra, Australia.

Now that the region has been clearly visualized, the Foursquare API was used to explore each suburbs and return the top 100 venues within 750 meters of the longitude and latitude for each postal code. Here is a head of the list Venues name, category, latitude and longitude informations from Forsquare API (Figure 3).

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figure3.png "Figure 3: Merged table of Suburbs and venues in Canberra.")


**Figure 3:** Merged table of Suburbs and venues in Canberra.

By counting the venues in each suburbs, we can see how some suburbs (the one in city centre such as Civic or the ones in entertainment regions such as Kingston) reached the 100 limit of venues. On the other hand; some regions are below 10 venues.

In summary there are 201 unique categories were returned by Foursquare, then I created a table which shows list of top 10 venue category for each region in below table. We can use later this table to figure out what theme or budget restaurant is appropriate for our business.

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figure6.png "Figure 4: list of top 10 venue category for each region in Canberra.")


**Figure 4:** list of top 10 venue category for each region in Canberra.

The extracted venue categories were encoded using one-hot encoding and the total restaurants in each region were calculated (Figure 5). 

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figure4.png "Figure 5: Result of calculating the number of restaurants in every suburb.")

**Figure 5:** Result of calculating the number of restaurants in every suburb.


I used unsupervised learning K-means algorithm to cluster the suburbs. K-Means algorithm is one of the most common cluster method of unsupervised learning.
With the resulting data of the number of the restaurants in each suburbs and the Median weekly personal income(A$) and Percentage of the ACT population we train a k-Means clustering algorithm with 6 clusters (Figure 6).

I used two methods to find out the best number of clusters. First I normalised my data. Then I used the first methode whitch was elbow method. As you can see in figure 7, the best number of cluster is 6.

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figureelbow.png: The Elbow Method showing the optimal k .")

**Figure 7:** The Elbow Method showing the optimal k.

Then I used the silhouette value to be sure that clustering is a good method for analyzing this project. silhouette value ranges from -1 to +1. Silhouette values close to 1 indicates a successful clustering operation and minus value means that clustering is not a good option for the analyzing. my values were all positive that indicate kmeans works for this project.


## Results

I merged related cluster information in the final table.

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figure8.png "Figure 8: The final table with cluster label .")

**Figure 8:** The final table with cluster label.

Below you can see the clustered map of Canberra.

This map has the below informations for each Suburb:

- Suburb name
- Cluster name
- Number of Restaurants
- Median weekley income


![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figure%20cluster.png "Figure 9: Result of the clustering algorithm.")

**Figure 9:** Result of the clustering algorithm.  

Also I normalised our data and created a bar chart to visualise better. It shows Total Restaurants, Median weekly personal income(A$) and Percentage of the ACT population in each suburb.

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figurebar.png "Figure 10: Bar chart.")

**Figure 10:** Bar Chart of Total Restaurants, Median weekly personal income(A$) and Percentage of the ACT population in each suburb.

Also you can see three pie charts witch shows Total Restaurants in each cluster and Median weekly personal income(A$) in each cluster and Percentage of the ACT population in each cluster.  

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figurepie2.png "Figure 11: the bar chart of Total Restaurants in each cluster.")

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figurepie3.png "Figure 11: the bar chart of Median weekly personal income(A$) in each cluster in each cluster.")

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/figurepie1.png "Figure 11: the bar chart of Percentage of the ACT population in each cluster.")


**Figure 11:** The pie chart of important criterias in each cluster 

## Discussion

Canberra is the capital of Australia with population of 426,704. It has 7 districts. It is a growing city and there is always a need for opening a restaurant. 

We can use different way of classification. I used the Kmeans algorithm for this project.

When I tested the Elbow method, I set the optimum k value to 6. 

I ended the study by visualizing the data and clustering information on the Canberra map. Also I visualize pie charts that show the important criterias to consider for opening a restaurant in each cluster. In future studies, the theme of restaurant or other details can be carried out for more study.


## Conclusion

Opening a restaurant is a complex task that can lead to a large monetary loss if not done properly. Thus, extensive research about the area would greatly increase the likelihood of the restaurant succeeding. From the project above, I demonstrated the workflow necessary for a client to determine what area the restaurant should open. 
