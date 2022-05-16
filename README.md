
# Phase 2 Project: King-County-Housing-Project

---

## Overview

The Argon Team consists of a team of respected data scientists with a combined experience of over 50 years. This highly sought team consisting of John Bruemmer, Woojin Jun and Nazar Mohl, uses their advanced knowledge of data and statistical techniques to gather, scrub, cleanse and analyze data to glean the meaningful information that may create a business advantage for clients.

---

## Business understanding

A midsized real estate developer in King County, Washington, has engaged the Argon Team to gather and analyze available data and determine what factors of a home most influence price and by how much. The Argon Team has identified trends in real estate prices in King County to determine a) the optimal locations in which to develop and b) the most potentially profitable housing configurations.

---

## Data understanding

The primary source of the available data was provided as a CSV file containing the King County House Sales dataset and was gathered between May, 2014, and May, 2015. It should be noted that the data is already several years old and King County (which includes Seattle) has continued to grow at a rate far exceeding the rest of the country. It has also recently experienced the effects of the global Covid pandemic. This data set predates these factors and therefore cannot reflect their impact if, indeed, there was an impact.

A secondary source of data was taken from the [point 2 website](https://www.point2homes.com/US/Neighborhood/WA/King-County-Demographics.html#MedianIncomeByZipcode). This provided population figures and the median and mean income of each zip code in King County.

---

## Data assumptions and preparation

The CSV file contained rows (entries) for 21,597 houses and included 21 columns of information for each house. 18 of these columns contained no nulls. Although the remaining 3 columns were between 82% and 89% complete, these particular housing features were not emphasized in the final analysis.

Apart from the date that the house was sold and the price at which it was sold, the data is either objective - related to a physical aspect of the house (# bedrooms, bathrooms, living area, etc.) or the location (zip code, longitude/latitude coordinates) - or subjective - related to the view, condition and overall grade.

Data was adjusted to drop records with extreme outlier values. A mid range priced house with 33 bedrooms seemed odd. Rather than have this extreme value skew the analysis, it was deemed appropriate to drop this record from the data.

Columns with categorical data was converted to numeric type so as to facilitate their inclusion in the models. New columns were derived/calculated as needed such as price per square foot.

Reasonable assumptions were made to replace certain null values such as in the waterfront column. A waterfront entry of 'YES' indicated that the house was a waterfront property. A 'NO' indicated that the house is not a waterfront property. A null was assumed to be a 'NO' and was replaced with this value.

---

## Data Analysis

Price was the only column that was deemed to be dependent. All others were deemed to be independent and were analyzed to identify if they correlated with and contributed to the price.

A heatmap was generated to identify which features might correlate with price and should be studied further.

The initial indication was that price correlated with the amount of living space (sqft_living), the number of bathrooms and the number of bedrooms.

  

---

## Modeling

Least Squares modeling technique was used to further clarify the relationship between price and these house features (sqft_living, bedrooms, bathrooms). The R Squared value was used to determine how well the various features of the models correlated with the price (target variable). R Squared value of around 0.45 was observed for price vs. sqft_living. Adding features such as bedrooms and bathrooms improved the R Squared value to .5.

A new approach was taken to include additional data in the models including the categorical data of "Grade" and Median Income of zip codes. Using One Hot encoding to represent the categorical values as numbers allowed for their inclusion in the models. The grade data increased the R Squared value to 0.6.

Additional categorical data of "View" and whether the property was "Waterfront", raised the R Squared value to 0.63. A final model pushed the R Squared value to 0.7.

Although more complicated metrics were explored, it would sacrifice the interpretability of the model. Ultimately, the decision was to keep the model simpler in an attempt to make it more accessible to our stakeholder. 
  

---

## Evaluation/Validation


   ![Final Model Residual and QQ Plot](/Images/final_model_graphs.png)
Our final model residual graph shows it is pretty evenly distributed between over and under estimating price. It has a slight lean towards overestimating price that should be analyzed further.

Additionally, the QQ plot shows that our model fails to accurately predict houses at either end of the extreme. Beyond two standard deviations from our average price our model becomes inaccurate. This is most likely due to high/low end houses having extremely specific reasons for their price. Our model is too general to account for these factors. 

Based off the coefficient for our model. We saw that with all other variables being equal a one dollar increase in median income affects the final price by $3.35. Additionally, we were able to see how grade affects a house from one grade to the next. 

![How Grade Affects Price](/Images/How_Grade_Affects_Price.png)


---

## Recommendations

Our recommendations are thusly to not focus on improving the grade of a house at the lower end. But heavily prioritize improving the grade of houses beyond 10. We saw an exponential relationship between grade and price meaning it is far more valuable to move up from 10-11 than it is to move from 5-6. This recommendation can also be used for building houses. It makes economic sense to reach a minimum grade of around 5 for new houses being built, but is likely not worth spending money to prioritize a higher grade for these types of houses. However, when building luxury homes achieving the highest grade possible will raise the price significantly. 

Additionally, using the coefficient values in our model for locations can give insight into finding undervalued homes in desirable locations. 

## Further Analysis

Using the data provided, a more complicated model could be made to improve its accuracy. This may lead to significant multi-collinearity complications and reduce the interpretability of any one variable. 

Additionally, more data could be gathered to improve our location metrics. Although median income served as a reasonable proxy for a neighborhood's desirability it's not a perfect predictor. Researching things such as school districts, walkability, or crime would improve the model.

## In Depth Analysis
If you would like to see more in depth analysis please see either the *[Jupyter Notebook](https://github.com/Jbruemmer/King-County-Housing-Project/blob/main/King%20County%20Development%20Recommendations.ipynb)* or the *[Slide Deck](https://github.com/Jbruemmer/King-County-Housing-Project/blob/main/King%20County%20Development%20Recommendations%20(Final).pptx)*.

If you would like to get in contact you can message Argon Team on Github or reach out to us:
#### John Bruemmer:
Github :[https://github.com/Jbruemmer](https://github.com/Jbruemmer)
Email: Johnnybruemmer@gmail.com, 
LinkedIn : [John Bruemmer | LinkedIn](https://www.linkedin.com/in/john-bruemmer-407a58a4/)

#### Woojin Jun:
Github: [https://github.com/WoojinJun](https://github.com/WoojinJun)
Email: [woojinjun93@gmail.com](mailto:woojinjun93@gmail.com)
LinkedIn: [https://www.linkedin.com/in/woojin-jun-6029bb114/](https://www.linkedin.com/in/woojin-jun-6029bb114/)

#### Nazar Mohl
Github: [https://github.com/NazarMohl](https://github.com/NazarMohl)
Email: [nazar.mohl@gmail.com](mailto:nazar.mohl@gmail.com)
LinkedIn: [https://www.linkedin.com/in/nazar-mohl/](https://www.linkedin.com/in/nazar-mohl/)




## Repository Structure
```
├── Images
├── Data
├── .gitignore
├── README.md
├── King-County-Development-Recommendations-Prices.ipynb
├── King-County-Development-Recommendations.pdf
└── King-County-Development-Recommendations-PDF.pdf

