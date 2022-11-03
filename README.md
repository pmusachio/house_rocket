# House Rocket
![bates.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/00.datasets/bates.png)

House Rocket is a digital platform whose business model is the purchase and sale of real estate using technology.
CEO needs to maximize the company's revenue by finding good business opportunities and the main strategy is to buy good homes in great locations at low prices and then resell them at higher prices.

## Business Problem
- Property purchase suggestions for a recommended value.
- Suggestions for selling properties for a recommended value.

## Business Assumptions
- Properties without bathrooms were discarded
- Duplicate ID's have been removed, considering only the most recent sale
- Properties with 33 bedrooms were considered a typo and changed to 3 bedrooms
- Location and condition of the property is key for the decision on wether to buy it or not
- Properties with a renovation date equal to 0 are properties that have never been renovated

## Solution Strategy
- **Property purchase suggestions for a recommended value**
    - Colect dataset from the Kaggle  ['house sales prediction'](https://www.kaggle.com/harlfoxem/housesalesprediction)
    - Data Cleaning and Transformation of variables.
    - Group properties by region (zipcode).
    - In each region, find the median property price.
    - Suggest properties that are below the median price in the region and that are in good condition.


- **Suggestions for selling properties for a recommended value**
    - Group properties by region (zipcode) and by seasonality ( Summer, Inter ).
    - In each region and seasonality, find the median property price.
    - Selling conditions:
        - purchase > median + seasonality | selling = purchase + 10%
        - purchase < median + seasonality | selling = purchase + 30%


- **Explore Data to find Insights for the business team**
    - Create an interactive Dashboard to Exploratory Data Analysis

## Top Insights
ID | Hypotheses | Graph | Translation for business
:-:|:-:|:-:|:-:
H01 | Properties that are waterfront are, in average, 30% more expensive | ![H01.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H01.png) | Houses with waterfront are 200% more expensive, it is better to invest on houses without waterfront, unless the profit is equally bigger
H02 | Properties built before 1955 are, in average, 50% less expensive | ![H02.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H02.png) | We can invest in newer properties because they are not much more expensive compared to those built before 1955
H03 | Properties without basement have a sqrt_lot 50% bigger than the ones with basement | ![H03.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H03.png) | If intend to invest in bigger lots, you should prioritize properties without a basement
H04 | Properties with higher number of bedrooms are, in average, 10% more expensive | ![H04.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H04.png) | Properties with 5 to 10 bedrooms are more expensive
H05 | Properties that were never renovated are, in average, 30% less expensive | ![H05.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H05.png) | Unrenovated properties are cheaper, and a great opportunity for appreciation
H06 | Older properties that were never renovated are 40% less expensive | ![H06.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H06.png) | Unlike insight H02, properties built before 1955 and W/O renovation are cheaper
H07 | Properties that were renovated recently are, in average, 16% more expensive | ![H07.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H07.png) | Recent renovations add value to properties, creating an opportunity to invest in properties without renovations to renovate them
H08 | Properties in bad condition but that are waterfront are, in average, 10% more expensive | ![H08.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H08.png) | Avoid properties in poor condition and waterfront, they are on average 5X more expensive, properties in good condition and waterfront are on average 2.6X more expensive
H09 | The YoY (Year over Year) growth of the price of the properties is of 10% | ![H09.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H09.png) | Price of real estate showed small variation (< 1%) between 2014 and 2015
H10 | The MoM (Month over Month) growth of the price of the properties is 15% | ![H10.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/H10.png) | Average price of the properties is higher between March and July

## Business Results
- **Total profit** (profit = selling price - buying price) of the properties in the portfolio is: **$1.120.337.411,00**

- **Property purchase suggestions for a recommended value**
![buy.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/buy.png)

- **Suggestions for selling properties for a recommended value**
![sell.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/sell.png)

- **Interactive Dashboard to Exploratory Data Analysis**
    [HOUSE ROCKET DASHBOARD](https://pmusachio-houserocket.streamlit.app/)
![dashboard.png](https://raw.githubusercontent.com/pmusachio/house_rocket/main/05.screenshots/dashboard.png)

## Conclusion
**Goals were achieved!!**   
The purchase and sale price recommendations were generated, as well as a suggestion of the best time to carry out the sale.

## Next Steps
According to insights H05 and H07, a viable way to increase profit would be to explore the possibility of buying unrenovated properties and renovating them.
