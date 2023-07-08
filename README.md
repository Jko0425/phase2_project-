# Predicting Housing Prices in King County, Seattle

## Overview

Prices of homes are always fluctuating. And with many companies looking at homes as investment pieces, it is imperative for these companies to purchase or sell these homes at optimal prices in order to maximize their profits. But how does a company know which price is fair and when to sell or buy? By looking at the data provided, specifically in King County, we can observe how the housing market has changed and create a predictive model that will return a fair price of a home.

## Business Problem

Investing in real estate can be risky, especially when there are many variables that may affect the price of a home. For instance, houses closer to the water may have greater demand and therefore have higher prices than houses inland. We need to find a way to properly isolate variables so that we can accurately predict housing prices and allow J.P. Morgan to potentially maximize profits or minimize their losses.

## Data

The data was provided by the [Flatiron School](https://github.com/learn-co-curriculum/dsc-phase-2-project-v2-5). It provideds details of homes in King County, Seattle. It contains homes sold/purchased between the years of 2021 and 2022. From the data, we can observe how price has changed throughout the years, and how each variable affects the price.

## Methodology

Firstly, we can see how the prices change according to time, especially in a post-COVID era. We can divide the sales of the homes according to their fiscal quarters. By taking the average prices of each quarter, we can plot the averages to observe the changes in price. We can also isolate each variable in order to determine which variable is most influential. To find the best model, we need to keep other variables constant. In our analysis, we will only look at homes with 8 rooms. If the model returns insufficient metrics (i.e. low r-squared values), we can isolate more variables and observe the metrics of the price vs. the isolated variable given that the prices are of 8 room houses. Once these models are created and the metrics are calculated, we can potentially find the best model for our recommendations.

## Results/Analysis

The data was separated according to their respective quarters and the average home price of each quarter was plotted. However, when observing the distribution of home prices, the data was severely skewed to the right. By taking the log of the prices, the data was normally distributed. The average of the log of prices was taken and the z-scores were calculated:
<p align="center">
  <img src="https://github.com/Jko0425/phase2_project-/assets/118938101/22d076f0-79f7-4c75-b938-2aca9cd4a6d0" width=50% height=50%>
</p>

Low z-scores indicate the averages were statistically significant.

![Changes in Price of Homes](https://github.com/Jko0425/phase2_project-/blob/5c8787703498fadcfc261bc43555931116032a9d/Graphs_Charts/Changes%20in%20Price%20of%20Homes.png)
The graph shows an upward trend in the year of 2022. It seems that the housing market has recovered from 2021 where the price decreased consistently throughout the fiscal quarters. To investigate why there is an increase or decrease in the housing market, we can look at mortgage rates, stock markets, or specifically how COVID-19 affect the county. More data is needed to further explore these hypotheses. However, we can confidently conclude that the prices are increasing as of 2022.

By separating the data according to their fiscal quarter, we found that homes with 8 total rooms (bedrooms + bathrooms) had a relatively high correlation value while having an adequate number of data. The regression results of the filtered data was obtained:
<p align="center">
  <img src="https://github.com/Jko0425/phase2_project-/blob/main/Graphs_Charts/Regression_results.png" width=75% height=75%>
</p>

The graph below contains data of 8 room homes in the second quarter of 2022. We are only looking at the most recent home sales because we do not want to over pay when purchasing, or overprice our homes as it can sit on the market without selling.
![Q2 2022 Prices of 8 Room Houses](https://github.com/Jko0425/phase2_project-/blob/5c8787703498fadcfc261bc43555931116032a9d/Graphs_Charts/Q2%202022%20Prices%20of%208%20Room%20Houses.png)
We can see how the price of 8-room homes change as a function of sqft of living space. In hopes of obtaining a higher r-squared value, we can dive further into this data and determine how each variables like `grade` or `condition` affects the price.

To determine how each category affected the price, we held the other variables constant. When investigating how `grade` affected the price, we only looked at data where homes did not have a `waterfront`, `nuisance`, or `greenbelt`. We also set the `condition` to average and `view` to none. The results ultimately returns this regression result:

<p align="center">
  <img src="https://github.com/Jko0425/phase2_project-/blob/main/Graphs_Charts/Regression%20results%20of%20grade.png" width=75% height=75%>
</p>

Using the coefficients from the results, we can construct an equation to predict prices:

<p align="center">
  <img src="https://github.com/Jko0425/phase2_project-/blob/main/Graphs_Charts/Multivariable%20equation.png" width=75% height=75%>
</p>

## Conclusion
We can determine the correct and fair prices of homes for the future from these results:
* __Housing market is on the upswing.__ The housing market seem to have recovered from the start of 2022. Therefore we can assume the price will follow a similar trend given nothing too substantial or deterimental happens in the economy.
* __We can determine the price of a home according to its square feet given the total room.__ We have specifically investigated how homes with 8 rooms differ in price according to their square footage, but this can be applied to other homes given sufficient data.
* __By keeping certain variables constant, we can see how other variables affect prices.__ A formula was derived that will allow us to calculate prices of homes depending on their `grade`. Formulas for other variables can be derived using the same method. The results for `grade` is posted as it had the greatest r-squared value.
### Recommendations
J.P. Morgan can follow these recommendations in an effort to maximize their profits:
* By observing the changes in the coefficients of `sqft_living`, we see that the prices and time have a direct relationship. Assuming no catastrophic event that would affect the economy, investing in real estate would benefit J.P. Morgan.
* We can also purchase homes with poor grades and renovate to a higher grade. Assuming the renovations are not too costly, our potential profit may be around $1.2 million.
