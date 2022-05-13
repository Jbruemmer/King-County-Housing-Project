# Phase 2 Project: King-County-Housing-Project
---
## Overview
The Argon Team consists of a team of respected data scientists with a combined experience of over 50 years. This highly sought team consisting of John Bruemmer, Woojin Jun and Nazar Mohl, uses their advanced knowledge of data and statistical techniques to gather, scrub, cleanse and analyze data to glean the meaningful information that may create a business advantage for clients.
---
## Business understanding
A midsized real estate developer in King County, Washington, has engaged the Argon Team to gather and analyze available data and determmine what factors of a home most influence price and by how much. The Argon Team has identified trends in real estate prices in King County to determine a) the optimal locations in which to develop and b) the most potentially profitable housing configurations.
---  
## Data understanding
The primary source of the available data was provided as a CSV file containing the King County House Sales dataset and was gathered between May, 2014, and May, 2015. It should be noted that the data is already several years old and King County (which includes Seattle) has continued to grow at a rate far exceeding the rest of the country. It has also recently experienced the effects of the global Covid pandemic. This data set predates these factors and therefore cannot reflect their impact if, indeed, there was an impact.  
A secondary source of data was taken from the ![point2 website](https://www.point2homes.com/US/Neighborhood/WA/King-County-Demographics.html#MedianIncomeByZipcode). This provided population figures and the median and mean income of each zip code in King County.  
---
## Data assumptions and preparation
The CSV file contained rows (entries) for 21,597 houses and included 21 columns of information for each house. 18 of these columns contained no nulls. Although the remaining 3 columns were between 82% and 89% complete, these particular housing features were not emphasized in the final analysis.  
Apart from the date that the house was sold and the price at which it was sold, the data is either objective - related to a physical aspect of the house (# bedrooms, bathrooms, living area, etc.) or the location (zipcode, longitude/latitude coordinates) - or subjective - related to the view, condition and overall grade.  
Data was adjusted to drop records with extreme outlier values. A mid range priced house with 33 bedrooms seemed odd. Rather than have this extreme value skew the analysis, it was deemed appropriate to drop this record from the data.  
Columns with categorical data was converted to numeric type so as to facilitate their inclusion in the models. New columns were derived/calculated as needed such as price per square foot.  
Reasonable assumptions were made to replace certain null values such as in the waterfront column. A waterfront entry of 'YES' indicated that the house was a waterfront property. A 'NO' indicated that the house is not a waterfront property. A null was assumed to be a 'NO' and was replaced with this value.
---
## Data Analysis
Price was the only column that was deemed to be dependant. All others were deemed to be independant and were analyzed to identify if they correlated with and contributed to the price.  
A heatmap was generated to identify which features might correlate with price and should be studied further.  
The initial indication was that price correlated with the amount of living space (sqft_living), the number of bathrooms and the number of bedrooms.  

---
## Modeling

---
## Evaluation

---
## Deployment

