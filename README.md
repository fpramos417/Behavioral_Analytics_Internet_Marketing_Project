# Internet Marketing Project
### Instructor: Dr. Zhou
### Authors: Fernanda Padilla & Julia Gittins

# Dataset
The question that this analysis attempts to answer is How can Media Contacts, a consulting company, help AirFrance increase their net revenue based on Return on Advertising (ROA) and online advertising? Our dataset includes financial and advertising data for Google, Yahoo, MSN, and Overture. There are 23 variables listed below.
['Publisher ID' 'Publisher Name' 'Keyword ID' 'Keyword' 'Match Type', 'Campaign' 'Keyword Group' 'Category' 'Bid Strategy' 'Keyword Type', 'Status' 'Search Engine Bid' 'Clicks' 'Click Charges', 'Avg. Cost per Click' 'Impressions' 'Engine Click Thru %' 'Avg. Pos.', 'Trans. Conv. %' 'Total Cost/ Trans.' 'Amount' 'Total Cost', 'Total Volume of Bookings']


# Exploratory Data Analysis
Bar Charts and Box Plots
We used bar charts and box plots to visualize the distribution of our data set. For the boxplots of Net Revenue, ROA, and Average Revenue per Booking, we calculated log to improve visualization of data distribution. After our exploratory data analysis, we did not use this calculated log anymore. 
Our statistical summary highlighted that 75% of our Net Revenue data is -1.60. 25% of our Net Revenue data is -18.87. Therefore, we can infer that publishers are overall experiencing losses. The standard deviation of the Net Revenue data is 14246.30, which is almost double of our mean. This suggests that data is widely distributed.
The Average Revenue per Booking is 1024.23, which is an overall gain for the publishers. The Average Probability of Booking is 0.007%, which is very low. The highest probability of booking is about 0.818%. It would be beneficial for the publishers to look closer at why the probability of booking is low. This insight will guide them to increase their performance.
The Average Cost per Click is 1.89, which is low compared to the max of 10.00 however not far off from the majority of the transactions, 75% of which are less than 2.66. This average cost of clicks should be a focus point for marketers to reduce. The mean is slightly higher than the median, which means that data distribution is skewed.
The Average Engine Click Thru % is 11.14, which is only slightly above the 75% percentile marker of 10.92. The standard deviation is higher than the mean, which suggests that data is widely distributed. Since the mean is almost double of the median, data is skewed.
From looking at this data and comparing the mean against the percentiles and maximum values, it looks like we might have some outliers in Engine Click Thru %, Trans. Conv %, and Avg. Cost per Click.
By using a Bar Chart analysis, we were able to compare different groups against each other and determine that after the unassigned campaigns, the highest cost of campaign is Air France Branded. We were also able to see that the most popular type of match used is “broad”. The least type of match used is “exact”.
Histograms
Histograms helped us visually understand the distribution of our data. The more we understand our data, the better recommendations we can make for Air France. The following are insights we gained on various factors through our data visualizations. 
Net Revenue: Net Revenue has a significant number of outliers. Most Net Revenue falls into the range of 0 and 100,000. Google - US has the highest Net Revenue while MSN - Global has the lowest Net Revenue.
Click: The Avg. cost per Click has a significant number of outliers. In addition, The lower number of clicks, the higher the cost per click. One click is the most common observation. Google - US has the highest average cost per click while MSN - Global has the lowest average cost per click.
ROA: ROA has few outliers. There is a slightly greater number of ROA observations on the lower quartile. Data for ROA is concentrated in the range of 0 and 500. We grouped publisher name by ROA to show which company is most successful via ROA. Air France may want to go with the highest ROA group to make the most accurate/positive decision for increasing net revenue. Yahoo - US has the highest ROA and MSN - US has the lowest ROA.
Revenue per Booking: Average Revenue per Booking has a considerable number of outliers. Data is distributed slightly more towards the lower quartile. Average Revenue per Booking is mainly within the range of 500 - 1000. While Google - US has highest Average Revenue per Booking. MSN - US has the lowest Average Revenue per Booking.
Probability/Volume of Booking: Google - US has highest probability of booking. The lowest probability of booking seems to be Overture - US. Google - US has the highest volume of bookings. MSN - Global has the lowest volume of bookings.
Impressions: Overture - Global has the highest number of impressions. MSN - US seems to have the lowest number of impressions.
Scatter Plots
Scatterplots are another visual method that we used to understand how our variables interact with each other. From our Scatterplots, we were able to determine that there is a potential positive relationship between Total Cost and Clicks and a slight potential positive relationship between Impressions and Total Costs. There are also plenty outliers.

Multicollinearity Issue
To determine if any of our variables were highly correlated with each other, we ran a correlational matrix. Based on the results, we were able to determine what variables could be dropped. We created dummy variables for categorical variables. From our Correlational matrix, we found out that many of our variables were not correlated with each other, which is beneficial to our analysis as each variable provides a unique perspective and measurement. We used a correlational coefficient greater or equal to 0.80 as a threshold for dropping one of the variables of the correlated pairs. We used 0.80 as our threshold because this value indicates a strong correlational coefficient. The following pairs of variables have correlational coefficients greater or equal to 0.80:
Click Charges and Clicks
Amount and Clicks
Total Volume of Booking and Clicks
Net Revenue and Clicks
Trans. Conv % and Return on Ad Spent (ROA)
Trans. Conv % and Probability of Booking
Amount and Total Volume of Bookings
Net Revenue and Total Volume of Bookings
Net Revenue and Amount
Additionally, we ran Variance Inflation Factor (VIF) testing on our independent variables. Clicks and Publisher Name scored higher than 5. None of our variables scored higher than 10. 
Considering the results of our correlation matrix and our VIF testing, we decided to use as our independent variables Impressions, Clicks, Trans. Conv. %, Avg. Pos., Total Volume of Bookings, Probability of Booking, Match Type (match_dum), Publisher Name (pub_dum), Campaign (camp_dum), Keyword (keyword_dum), Keyword Group (keygroup_dum), Category (cat_dum), Bid Strategy (bids_dum), and Status (status_dum).


# Interpretation of Regression Results
We removed any variables that had a p value over 0.05. This included our coefficient, which had a high p value. Our Estimated Regression Equation was:
Total Cost = -0.0005 Impressions + 1.7756 Clicks -70.4944 Total Volume of Bookings + 130.5588 match_dum + 326.4621 camp_dum + 1616.1791 keyword_dum -582.3154 cat_dum -64.8467 bids_dum
In addition to the description of magnitude and direction of impact of our independent variables, please find our interpretation of our results below:
Impressions has a negative weak relationship with Total Cost. When there is one more impression, total cost will slightly decrease. This could be because impressions could be sold in bulk. This could cause a very loose decrease in total cost for the provider. 
Clicks has a positive relationship with Total Cost. When there is one more click, the total cost will increase. If the advertiser is only paying for the ads that were clicked, the total cost could slightly increase for the publisher. 
Total Volume of Bookings has strong negative relationship with Total Cost. When the volume of bookings increases by one unit, the total cost will decrease by 70. This is likely due to bulk purchases that often include a discount in total price paid to the advertiser.
Type of match (match_dum) has a strong positive relationship with Total Cost. When the type of match is broad, the total cost will increase by $130. This indicates it is more expensive for the advertiser to use a broad word search on advertisements. Even though a lot of people may click on the advertisement, it will not produce the desired results because the click will not compare to the specific transaction. 
Campaign has a strong positive relationship with Total Cost. When campaign is Air France branded, the total cost will increase by $296.51. This could be due to the fact that when a customer clicks directly on an Air France advertisement making it a more efficient transaction but more costly for advertisers who are paying based on the ads that are clicked. 
Keyword: Keyword has a strong positive relationship with total cost. When the keyword is “Air France”, the total cost will increase by about $1616.18. This could be due to the fact that purchasers are routed more directly to the page/transaction they are looking for. Like the Campaign variable above, although it is cost effective for the purchaser, it is more costly for the advertisers who pay based on clicked ads, which are reduced when there is a more direct pathway. 
Category: has a strong negative relationship with total cost. When the category is “Airline”, the total cost will decrease about $582.32. Based on the bar chart results in the exploratory data analysis, we can see that because Airline is an “exact” term, price will decrease dramatically. 
Bids has a strong negative relationship with total cost. When the bid is “Position 5-10 Bid Strategy”, the total cost will decrease by about $64.85. The total cost will decrease because the advertisement is less likely to be clicked in comparison to the advertisements in the 1st through 4th position. 

# Conclusion and Recommendations 
Keyword, Category and Campaign are the best predictors of total cost because the magnitude of all of them is greater than 300 which shows a very strong predictive relationship. 
As such, we suggest that Air France use Google to increase their share in the competitive US markets because Google performed the best of all providers. We recommend that their strategy should be to have a key word of “Air France”, a category of “Airlines” and advertisements populating in a bid position between 5 and 10.
