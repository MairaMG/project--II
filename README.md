# Project II: Michelin Guide 2023- A Brief Data Analysis
## 1. Introduction 
The aim of this project is to select, import, clean and format a dataset to build a data pipeline that processes the data and that produces a result. The visualizations will either prove or disprove my hypotheses.

DataFrame Shape: 6992 x 14

Columns Information: name, address, location, cuisine, price (as currency symbol dependending on the country ie. €,€€,€€€,€€€€ for UE countries), longitude, latitude, phone number, Michelin Guide url, website url, award, facilities and services, description. 

## 2. Dataset 

- 2023 Michelin Guide Restaurants Dataset - Kaggle
- Google Places (API)

Links:
https://www.kaggle.com/datasets/ngshiheng/michelin-guide-restaurants-2021

https://console.cloud.google.com/marketplace/product/google/places.googleapis.com?q=search&referrer=search&project=summer-artwork-403510

## 3. Methodology
Steps followed:
1) Identify a Dataset in Kaggle
2) Collection of additional data with the Google Places API
3) Cleaning and Transforming the data
4) EDA
5) Visualization

Libraries used:
- Pandas as pd
- Numpy as np
- Matplotlib.pyplot as plt
- Seaborn as sns
- Re
- Pycountry
- Plotly.io as pio
- Plotly.express as px
- Geopandas as gpd

## 4. Goals / Hypothesis 

1) Restaurant Distribution:

•	Objective: Analyze the geographical distribution of Michelin-rated restaurants.

•	Hypothesis 1: France is the country with most Michelin-rated Restaurants (where the Michelin Guide was launched).

•	Hypothesis 1.2: Michelin-rated restaurants are not mainly located in capital cities.

2) Price Range and Ratings:

•	Objective: Investigate the relationship between the price range, the awards and the customer ratings.

•	Hypothesis 2: Higher Michelin Awards tend to have Higher Google Ratings

•	Hypothesis 2.1: Higher-priced restaurants tend to have higher Google Ratings.

3) Cuisine Popularity:

•	Objective: Identify popular cuisines among Michelin-starred restaurants and find out the prefered cuisine per country.

•	Hypothesis 3: Modern Cuisine is the most popular within Michelin-Starred Restaurants

4) Location-Based Analysis:

•	Objective: Explore the top Michelin-rated Restaurants in Barcelona to save on your Google Maps account.

•	Hypothesis 4: Barcelona's Disfrutar restaurant was recently awarded as the 2nd best restaurant in the world by "The World's 50 best restaurants" ranking. 

Hyphotesis is that Disfrutar will show up as one of the top Michelin-Starred restaurants in Barcelona according to customers ratings.

•	Hypothesis 4.1: Barcelona is the city with more Michelin-Starred restaurants in Spain.

## 5. Analysis 

For the analysis I created the following columns: country, city, price_convention(directly related to the Price column), and rating (this information was collected with the API)

Disclaimer: I only have available 2023 Michelin Guide information, and thus I was not able to compare this data with past trends. In addition, the API couldn't retrieved the rating for all Michelin-rated restaurants (missing ratings = 18%). Due to the narrow scope of this dataset, the insight I derive from my analysis may be limited.

Insights:
1) Restaurant Distribution: 
- The cities with most Michelin-rated restaurants are in Japan.
2) Price Range and Ratings:
- When analys¡zing the Price column I realized there were different currencies (related to the country) to indicate the same idea for each type of value. Then, I created a new column named 'Price_convention' to standarize the significance of the Price column. As following:
ie. €, €€, €€€, €€€€
    - For all prices with 1 currency symbol I replaced it with a new value: 'Inexpensive"
    - For all prices with 2 currency symbols I replaced it with a new value: 'Moderately"
    - For all prices with 3 currency symbols I replaced it with a new value: 'Expensive"
    - For all prices with 4 currency symbols I replaced it with a new value: 'Very Expensive"
- Higher-priced restaurants tend to have higher Google ratings, although there is still considerable variability within each price category.
- Restaurants with more Michelin stars tend to have higher Google ratings.
3) Cuisine Popularity:
- Modern cuisine, that is the one that always strive to produce the most delicious, technically exquisite food, and always apply analytical thinking and creativity to constantly advance the face of cuisine, is the most chosen type of cuisine by Michelin-starred restaurants. 
4) Location-Based Analysis:
- Barcelona with 24 Michelin-rated restaurants, is the Spanish city with the highest number of Michelin stars. 


## 6. Results
1) Restaurant Distribution: 
-  The first part of the hypothesis is true. France is the country with most Michelin-rated restaurants. The second part of the hypothesis is mostly true for european countries. However, in asian and southamerican countries, michelin-rated restaurants are mostly located in the capital city.
2) Price Range and Ratings:
- The boxplot supports the hypothesis that restaurants with more Michelin stars tend to have higher Google ratings. The trend is clear and consistent across the different Michelin star categories.
3) Cuisine Popularity:
- The hypthoesis is true. There is a clear difference  between the Moder Cuisine and the next category that in this case is "Creative".
4) Location-Based Analysis:
- Disfrutar is indeed in the top 3 list of the 2 Starred-Michelin Restaurants.

## 7. Conclusions  
- Most Michelin-rated restaurants are located in european countries.
- When restaurants have more stars, the price is very expensive and the customers rate them better.
- The most selected cuisine by Michelin-starred restaurants is Modern Cuisine.

## 8. Links  
Canva link: https://www.canva.com/design/DAFywnM7XMU/zreBGcvAgemuCxOWr_1bCA/view?utm_content=DAFywnM7XMU&utm_campaign=designshare&utm_medium=link&utm_source=editor