# Agricultue-Production-and-Climate-Change
An Exploratory Analysis of Agriculture, Water and Air Particulates in relation to Produce

![image](https://github.com/vileincorp/Agricultue-Production-and-Climate-Change/assets/124652720/eccc451f-863a-4602-98c0-4f6c8f6133b4)


Corrected spelling:

General Overview:

The backbone of any civilization is its ability to properly feed its population through sustained agriculture. Climate change is a novel threat to humanity, and we can only model a myriad of potential effects. Nevertheless, I wanted to explore and generate a way for us to understand what climate change might mean for agriculture production: "Climate Change, not Climate death." So, through the data, I sought to answer:

- What were the highest and lowest values in agriculture production over the last 28 years?
- How does air and water quality influence production over that time span?
- Could we predict future production based on variance in these patterns?

The goal of this project is to help farmers and climate scientists discover the best way to grow the right crops in a changing climate, as well as entrepreneurs and businesses articulate their investment positioning for the future when produce types we take for granted might be harder to grow.

Business Understanding:

Farmers make up roughly 1% of the population, and according to the USDA, their median age is near 60. Despite the US in total representing 5% of the world's population, it accounts for 15% of the world's agricultural suppliers for the world at large, with California accounting for 4% of that total. California, a land with increasingly extreme droughts and already with a burgeoning population, is home to some of the most profitable and fertile valleys in the world.

With the advent of Robotic AI to offset the farmer population aging out, it is important to implement technology not only in labor but also in the generative aspect, i.e., choosing what to plant.

Using this data and modeling, we can graph and better predict changes in agriculture stemming from climate and prepare our farms to produce not only what has a higher yield but better survivability.

Data Understanding:

The data was independently sourced from the USDA's NASS and NRCS divisions, as well as the PRB, over the last 28 years. Ranging from Yield, Air Particulates, Chemical Composition (Macro and Micro Nutrients), Electrical Conductivity, and more.

In total, there were roughly 50+ original factors over 80,000+ entries that were filtered down to the 16 most important factors and 30,000 entries yet representing the most important regions, agricultural outputs, and chemical factors over 28 years.

Data info:

- Production: https://www.nass.usda.gov/Statistics_by_State/California/Publications/AgComm/index.php
- Air Quality: https://shorturl.at/oxU02
- Chemical Composition: https://www.nrcs.usda.gov/resources/data-and-reports/ssurgo/stats2go-metadata

Data Prep:

In total, there were about 80,000 entries across 50+ some columns, so cleaning not only the formatting but also disposing of irrelevant information was my first priority. There were numerous minute differences between each group, but with the help of some functions, I was able to standardize everything. After standardization, I began to explore the data to find the best sampling of counties and crops in df_3 and found overlap with available information in df_1 and df_2, leading me to Stanislaus, Tulare, and Fresno for Grapes, Walnuts, and Hay Alfalfa. From there, the data was saved off individually and run through a few different modeling and cross-validation techniques.

Models:

First, I examined how the data would appear over a forecast. Then, I ran an AdFuller test to test if it was stationary, and then an Auto-correlation and Partial Auto-correlation. Finally, after that, I ran an ARIMA model, which I found more suitable than a SARIMAX given the time increments of my data (yearly). Using

 a search and test function for PDQ, I found which inputs generated the best model and began validating against the MSRE as a metric for error. I ran a few split tests with a few different kinds of P, D, Q just to see the differences in results and a y-hat test to try to perfect the model, including a naive Bayes. Lastly, I forecasted into the future about 5 years on each model.

Evaluation:

Expected Yields - Looking at the last 29 years, I was able to build a predictive model with a few variations for testing and able to predict the production numbers of crops in the next 5 years with model effectiveness ranging from 15% to 30% RMSE, meaning that I am able to predict the given yield of an upcoming year with about 85% to 70% accuracy.

Chemical Effects - There is an overall trend of acidification in the dataset, and when using the Predictive Regression model, we can see how certain crops like grain greatly decrease in yield. So, focusing on plants that like acidification or implementing meditative practices to help offset this is paramount.

Conclusion: 
Models: 
 Fresno Walnuts 19,000 - test - 1,973 / training - 1,739 / Naive 1,262 = 87%
 Tulare Walnuts 80,000- Test - 13,011 / Training 14,665 / Naive 19,581 = 81%
 Merced Walnuts 11,000- Test - 2,876 / Training 3,664 / Naive 1,913 = 75% 
 
 Fresno Grapes 750,000 - Test - 211,951 / Training 196,479 / Naive 71,343 = 79%
 Merced Grapes 145,000 - Test - 8,657 / Training 37,924 / Naive 25,668  = 84% 
 San Joaquin Grapes 700,000 - Test - 121,919 / Training 184,156 / Naive 151,745 = 79% 
 
 Fresno Alfalfa - 180,000 - Test - 36,232 / Training - 37,924 / Naive 98,638 = 69%
Tulare Alfalfa - 360,000  - Test - 44,361 / Training 37,924 / Naive 81,816 = 85%
Stanislauski Alfalfa - 125,000 - Test - 69,950 / Training - 9,342 / Naive 49,835 = 66% 

There are a variety of factors that can influence production, but one of the most significant in the fight against climate change is what is actually planted and the environment in which it exists. Through these models, we can better understand what we might harvest from the earth and how we can maximize those yields.

Areas for Improvement:

1. Human Seasonality: Gas, AC, and microplastics are released seasonally, which may influence outputs. Further investigation into this aspect can provide valuable insights.

2. Bills vs Yields: Agriculture and climate change are subsidized and can influence production. Therefore, it is important to examine legislation and how it might impact production, such as the case of corn.

3. Further Data: Some of the underlying datasets were incomplete. Comparing readings from adjacent regions, for example, a county over, could provide a reasonable basis for obtaining additional insights.


Repository File Structure
├── Images (for readme, presentation)
├── Final Political Presentation (pdf Presentation)
├── Time_Series_Notebook.ipynb
├── Zillow Data (dataset)
└── README.md

