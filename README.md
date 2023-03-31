# Predicting Housing Prices in King County, Seattle

## Overview

Prices of homes are always fluctuating. And with many companies looking at homes as investment pieces, it is imperative for these companies to purchase or sell these homes at optimal prices in order to maximize their profits. But how does a company know which price is fair and when to sell or buy? By looking at the data provided, specifically in King County, we can observe how the housing market has changed and create a predictive model that will return a fair price of a home.

## Business Problem

There are many variables that may affect the price of a home. For instance, houses closer to the water may have greater demand and therefore have higher prices than houses inland. To properly calculate these prices, we can isolate each variable in order to determine which variable is most influential. This can be done by keeping certain variables constant.
Another problem may be looking at home prices in previous years. The housing market is similar to the stock market in that it changes through time. Although it may be useful to look at prices from previous years to predict trends, the prices of homes will be reactionary to the latest data.

## Data

The data was provided by the [Flatiron School](https://github.com/learn-co-curriculum/dsc-phase-2-project-v2-5). It provideds details of homes in King County, Seattle. It contains homes sold/purchased between the years of 2021 and 2022. From the data, we can observe how price has changed throughout the years, and how each variable affects the price.

## Results/Analysis

The data was separated according to their respective quarters and the average home price of each quarter was plotted. However, when observing the distribution of home prices, the data was severely skewed to the right. By taking the log of the prices, the data was normally distributed. The average of the log of prices was taken then plotted.
![Changes in Price of Homes](https://github.com/Jko0425/phase2_project-/blob/5c8787703498fadcfc261bc43555931116032a9d/Graphs_Charts/Changes%20in%20Price%20of%20Homes.png)
The graph shows an upward trend in the year of 2022. It seems that the housing market has recovered from 2021 where the price decreased consistently throughout the fiscal quarters. To investigate why there is an increase or decrease in the housing market, we can look at mortgage rates, stock markets, or specifically how COVID-19 affect the county. More data is needed to further explore these hypotheses. However, we can confidently conclude that the prices are increasing as of 2022.

This graph contains data of homes that have a total of 8 rooms (bedrooms + bathrooms) in the second quarter of 2022. We are only looking at the most recent home sales because we are trying to derive a fair price for either the buyer or seller.
![Q2 2022 Prices of 8 Room Houses](https://github.com/Jko0425/phase2_project-/blob/5c8787703498fadcfc261bc43555931116032a9d/Graphs_Charts/Q2%202022%20Prices%20of%208%20Room%20Houses.png)
We can see how the price of 8-room homes change as a function of sqft of living space. We can dive further into this data and determine how each variables like `grade` or `condition` affects the price.

To determine how each category affected the price, we held the other variables constant. When investigating how `grade` affected the price, we only looked at data where homes did not have a `waterfront`, `nuisance`, or `greenbelt`. We also set the `condition` to average and `view` to none. The results ultimately returns this formula:

![Multivariable equation of the categorical values of grade](https://github.com/Jko0425/phase2_project-/blob/e2c171ff8f25911d8d93c9b4fed98eb073e77b9d/Graphs_Charts/Multivariable%20equation%20of%20the%20categorical%20values%20of%20grade.png)
This formula can be used to determine a fair price of an 8-room home. Each of the coefficients have p values less than 0.05, and therefore are significant.

## Conclusion
We can determine the correct and fair price of homes for the future from these results:
* __Housing market is on the upswing.__ The housing market seem to have recovered from the start of 2022. Therefore we can assume the price will follow a similar trend given nothing too substantial or deterimental happens in the economy.
* __We can determine the price of a home according to its square feet given the total room.__ We have specifically investigated how homes with 8 rooms differ in price according to their square footage, but this can be applied to other homes given sufficient data.
* __By keeping certain variables constant, we can see how other variables affect prices.__ A formula was derived that will allow us to calculate prices of homes depending on their `grade`. Formulas for other variables can be derived using the same method. The results for `grade` is posted as it had the greatest r-squared value.
