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

The next step was to visualize the location of the various postal codes within Canberra to obtain a general understanding of the location (Figure 2). As we can see

![alt text](https://github.com/neda-ale/Coursera_Capstone/blob/main/Figure2.jpg "Figure 2: Location of each postal code within Canberra, Australia.")

**Figure 2:** Location of each postal code within Canberra, Australia.
