# VALUE ANALYSIS FOR HOUSE SALE PRICES IN KING COUNTY
Name: Julie chepngeno

# Introduction
At a Real Estate, buying or selling a home is one of the most significant financial decisions you'll make in your life. Our goal is to make the home buying or selling process as smooth and stress-free as possible for our clients. In this project,we will be analyzing house sales in a western county which can be found in kc_house_data.csv

 The real estate market serves as a reflection of societal aspirations, investment opportunities, and the pursuit of the elusive "dream home." Whether it's residential, commercial, or industrial, real estate offers a multitude of possibilities for individuals, businesses, and communities.It involves home owners looking to sell their property and home buyers looking to buy a dream home

Problem statement
The  real estate agency needs to develop a comprehensive advisory framework to assist homeowners in understanding the potential value-adding effects of specific home renovations. This framework should include detailed information on the types of renovations, their estimated costs, and the potential increase in the property's value. By addressing this problem, the agency can empower homeowners to make informed decisions, thereby increasing their satisfaction, trust, and the likelihood of engaging the agency's services.

Main objective
The main objective of the real estate agency's initiative is to provide homeowners with accurate and valuable advice regarding home renovations and their potential impact on the estimated value of their properties

specific objectives
Develop a Comprehensive Renovation Advisory Framework: The agency aims to create a structured framework that outlines different renovation types and their potential impact on property value.

Track Success Metrics: The agency will track key success metrics, such as the number of homeowners served, the percentage of clients who reported increased property value, and the number of referrals received.

Data understanding

In this project, the data was collected from a CSV (Comma-Separated Values) file. The dataset, kc_house_data.csv, contains information related to real estate properties in King County, Washington. It includes various attributes that describe the properties, such as their location, size, condition, and sale prices.

Analyzing the data set will help us to provide advice to homeowners about how home renovations might increase the estimated value of their homes, and by what amount.

EDA
From our analyis,the condition ratings are converted into a discrete variable.
The changes show from 1 to 5,where the lowest has 1 as poor,with the midpoint 3 as average,and the highest 5 as very good 

There is no much difference between the quarters except that the average price in quarter 2 is slightly higher than the rest.There are columns in the dataset that may not be useful in evaluation and we drop them by initializing the list called dropped and then dropping thm from our dataset<img src = images2\output1.png>

 A majority of the price distributions lie between 0 and 1.2 million with those beyond this considered as outliers. On the other hand, we consider these prices to be important for our analysis except those above 5 million that we considered as
genuine outliers which we will drop<img src = output2.png >

 The column 'grade' is split for its values and only the first section is singled out to be converted into numeric type and used as a scale for measuring the grade of the houses / properties Shifting has been done so that the grading parameters may start from 1. From 1 to 11, where the lowest has 1 as poor, with a midpoint of 7 as average and the highest being 11 as mansion

 Modelling
  There is a very high correlation between the predictor columns of'sqft_above', 'sqft_living', 'sqft_living15, 'grade',and 'bathrooms'. Dropping some of these will eliminate multicollinearity features. The columns to drop will be 'sqft_above', 'sqft_living15', 'grade',and 'bathrooms'<img src = output3.png>

  The model is generally statistically sigmificant at a significance level of with a _value of 0.0, and explains about 49% of the variance in price.The constant and coefficient are statistically significant. For a unit increase in square-foot living area, we see an associated increase in 275 dollars in selling price of the
houses.<img src = output4.png>

The centred model is statistically significant as standard alpha of 0.05 being 0.0, and still explains 58% of the variance in sale price.The centred model still explains the same amount of variance as the multiple model.The model coefficients are statistically significant except for "sqft_lot".The constant here explains that for an average house that is not renovated, with no waterfront and built since
1900, we would have a sale price of 711,600 dollars.

Transformations
log transformations did not assist in improving improving the model. The adjusted r-squared value remained constant. This led to the need for considering other features affecting the variability in selling price


Standard Errors assume that the covariance matrix of the errors is correctly specified.The condition number is large, 5.47e+06. This might indicate that there are
strong multicollinearity or other numerical problems.<img src = output5.png>

Findings
* The multiple linear regression model has an R-squared value of 0.79, which indicates that the model can explain 79% of the variance of the market
house sale prices which is a good sign that the model is effective in predicting the prices 
* The waterfront view was seen to be most impactful with houses having a waterfront view having value increase of about 834,000 dollars more than those
without a waterfront.This can be inferred for the other variables as well
* For an average house that is not renovated, with no waterfront and built since 1900, we would have a sale price of 711,600 dollars
* The combination of square footage of the living area, bedrooms, floors, and whether the property had a waterfront view or was renovated are the most
reliable predictors of a house's price in King County.

Recommendations
* We recommend for customers on a budget should look out for houses situated on higher property floors as we expect a price drop on said houses of about
30,000 dollars for every floor increase
* Development of a comprehensive database the agency can use to track the renovation projects that would improve property value.
* For customers who would like to sell their properties/houses, it is recommended that they should renovate them first as we see these would be an
increase in value by about 48,000 dollars

Conclusion

* The combination of square footage of the living area, bedrooms, floors, and whether the property had a waterfront view or was renovated are the most
reliable predictors of a house's price in King County.
* There were some limitations to the model. To meet regression assumptions, we had to try out log-transformation on certain variables. Therefore,any new data used with the model would require similar preprocessing. Additionally, since housing prices vary regionally, the model's usefulness for data from other counties may be restricted.
* If you are seeking affordable housing, it may be advisable to compromise on square footage and have no waterfront view. But, given that
many urban residents already do this, it may not be a viable solution for everyone

Next Steps
* Using datasets from other counties to be able to better advice our customers from comparing the dataset results.
* The agency may prepare questionnaires to identify their strengths, weaknesses, opportunities and threats and use this information to prioritize
recommendations that would help address their weaknesses and take advantge of their opportunities and strengths.
* It is also important for the agency to continuously monitor the effectiveness of the strategies they implement and make adjustments as necessary. This
could involve tracking metrics like website traffic, this model, social media engagement, and lead generation to assess the impact of their efforts and
identify areas for improvement.
* More research is required to have a more integrated and informative dataset finding more factors that influence the price

