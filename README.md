# **Data Analysis on hundreds of Coffee Shops in BGC, Philippines’ central business district.**

## Objective of the project:

1. Identify most popular coffee shops in BGC and uncover how they fare in terms of menu quality (drink variety and affordability) and alt-milk friendliness.

## Project findings:

1. There are almost 200 coffee shops located within the 240-hectare area of BGC.
2. High popularity scores do not necessarily correlate with high scores in menu quality or alt-milk friendliness. These variables are not tied to one another.
3. People’s choices in coffee shops are hinged on both tangible and intangible reasons.

## Summary of the data collection process:

### Google Places

1. Utilized Google Places API to scraped through thousands of establishments in the Philippines and isolate data on coffee-serving businesses within BGC.
2. Saved the findings into a dictionary JSON file .
3. Converted the said file into a Pandas Database and normalized the data ([Source](https://stackoverflow.com/questions/21104592/json-to-pandas-dataframe)).

### GrabFood Marketplace

1. Manually scraped data (menu items, prices, alt-milk options) on the Top 10 Most Popular BGC Coffee Shops
2. Documented on Google Sheets

## Overview of the data analysis process

### Using Python

1. Created a ‘Popularity Score’ for each coffee shop:
    1. Normalized figures for (1) rating and (2) review count.
    2. Multiplied normalized rating (nRating) and normalized review count (nReviewCount) by weighted ratios (0.6 for rating and 0.4 for review count) and combined them to get the final "Popularity Score" for each coffee shop.
2. Ranked coffee shops by their Popularity Scores.
3. Filtered the Top 10 unique* coffee shops into a CSV.
    
    *Note: Initially, I attempted to aggregate the popularity scores of coffee chains with multiple branches into a single score. However, I felt like this approach misrepresented the data and disadvantaged the chains. Therefore, I decided to keep only the highest-scoring branch of each chain and omit the others.
    

### Using Google Sheets

1. Combined data on Top 10 BGC coffee shops with their respective menu items, prices, and alt-milk offerings into a Google Sheet.
2. Created a ‘Menu Quality Score’ for each coffee shop
    1. Normalized figures for (1) coffee menu items  and (2) average price
    2. Multiplied normalized coffee menu items and normalized average price  by weighted ratios (0.5 for rating and 0.5 for review count) and combined them to get the final "Menu Quality Score" for each coffee shop.
3. Created an ‘Alt-milk Friendliness Score’ for each coffee shop
    1. Normalized figures for (1) alt-milk options  and (2) alt-milk average price
    2. Multiplied normalized alt-milk options and normalized alt-milk average price by weighted ratios (0.5 for alt-milk options and 0.5 for alt-milk average price) and combined them to get the final "Alt-milk Friendliness Score’" for each coffee shop.
    
    ew skills, approaches, etc you used, or where you grew the most during the project
    
- A section about things you tried to do or wanted to do but did not have the skills/time (but if you have more time you might do)

## Lessons learned; Scope and Limitations

1. Google Places API has a 60-item result limit:
    
    Initially attempted to do a comparison on biggest coffee chains in Metro Manila. This includes the likes of Starbucks, Dunkin, Coffee Bean & Tea Leaf etc. Went as far as creating a JSON file per Coffee Chain and uploading each individually on Pandas, but got suspicious when I did not find branches I personally frequented in my database results. 
    
    Eventually realized that Google Places API had a 60-item result limit, making it difficult to collect the total number of branches in 1 go due to the constraints in the technology. Pivoted to a smaller parameter instead, focusing on coffee shops within the area of BGC.
    
2. Grab Food > Food Panda in terms of menu completion
    
    While both Grab Food and Food Panda displayed the same drink items and prices, the Grab app was more complete in terms of add-on items such as alternative milk options.
    
3. Make your viz go through the “Mom Test”
    
    To truly dummy-proof your viz and make it as clear and concise as possible, ask non-technical friends and family to read through your charts and analysis. Their feedback will be full of valuable questions and suggestions that will help make your project more understandable to the lay reader.
    
4. Underpinning other factors behind popularity:
    
    While my study primarily focused on Menu Variety, Affordability, and Alt-Milk Friendliness as variables alongside a shop’s popularity, I would also like to consider possible factors outside of this. Examples include [1] density of office buildings around a shop’s geo-location, [2] brand and social media identity, [3] availability of wifi and other amenities, etc.
    

## Data and Notebooks used

Found in the same Git Repository

## Link to project page

https://juliana0ng.github.io/LedeProject1/
