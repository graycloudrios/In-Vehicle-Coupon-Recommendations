# In-Vehicle Coupon Recommendations
## **Code and Data necessary for completion of assignment 5.1**


**Author**: Graycloud Rios

File Structure:

  ./ - Directory containing Jupiter Notebook and README file
  
  Files:
  
  [coupon-notebook.ipynb](https://github.com/graycloudrios/assignment-5.1/blob/main/coupon-notebook.ipynb)

  README.md - This file
  
  ./data - Directory containing the data file

  Files:
  
  [coupons.csv](https://github.com/graycloudrios/assignment-5.1/blob/main/data/coupons.csv)

  The notebook file associated with this assignment can be found here **==>>** [coupon-notebook.ipynb](https://github.com/graycloudrios/assignment-5.1/blob/main/coupon-notebook.ipynb)

## Data Description
The data provided consists of observations of the responses given when an in-vehicle coupon is offered. The acceptance or refusal is recorded along with data regarding the individual responding. The data can be described as follows ( [column descriptions obtained here](https://archive.ics.uci.edu/dataset/603/in+vehicle+coupon+recommendation) ):

* destination: No Urgent Place, Home, Work
* passanger: Alone, Friend(s), Kid(s), Partner (who are the passengers in the car)
* weather: Sunny, Rainy, Snowy
* temperature:55, 80, 30
* time: 2PM, 10AM, 6PM, 7AM, 10PM
* coupon: Restaurant(<$20), Coffee House, Carry out & Take away, Bar, Restaurant($20-$50)
* expiration: 1d, 2h (the coupon expires in 1 day or in 2 hours)
* gender: Female, Male
* age: 21, 46, 26, 31, 41, 50plus, 36, below21
* maritalStatus: Unmarried partner, Single, Married partner, Divorced, Widowed
* has_Children:1, 0
* education: Some college - no degree, Bachelors degree, Associates degree, High School Graduate, Graduate degree (Masters or Doctorate), Some High School
* occupation: Unemployed, Architecture & Engineering, Student, 
* Education&Training&Library, Healthcare Support, 
* Healthcare Practitioners & Technical, Sales & Related, Management, 
* Arts Design Entertainment Sports & Media, Computer & Mathematical, 
* Life Physical Social Science, Personal Care & Service, 
* Community & Social Services, Office & Administrative Support, 
* Construction & Extraction, Legal, Retired, 
* Installation Maintenance & Repair, Transportation & Material Moving, 
* Business & Financial, Protective Service,
* Food Preparation & Serving Related, Production Occupations, 
* Building & Grounds Cleaning & Maintenance, Farming Fishing & Forestry
* income: $37500 - $49999, $62500 - $74999, $12500 - $24999, $75000 - $87499, 
* $50000 - $62499, $25000 - $37499, $100000 or More, $87500 - $99999, Less than $12500
* Bar: never, less1, 1~3, gt8,  nan4~8 (feature meaning: how many times do you go to a bar every month?)
* CoffeeHouse: never, less1, 4~8, 1~3, gt8,  nan (feature meaning: how many times do you go to a coffeehouse every month?)
* CarryAway:n4~8, 1~3, gt8, less1, never (feature meaning: how many times do you get take-away food every month?)
* RestaurantLessThan20: 4~8, 1~3, less1, gt8,  never (feature meaning: how many times do you go to a restaurant with an average expense per person of less than $20 every month?)
* Restaurant20To50: 1~3, less1, never, gt8, 4~8,  nan (feature meaning: how many times do you go to a restaurant with average expense per person of $20 - $50 every month?)
* toCoupon_GEQ15min:0,1 (feature meaning: driving distance to the restaurant/bar for using the coupon is greater than 15 minutes)
* toCoupon_GEQ25min:0, 1 (feature meaning: driving distance to the restaurant/bar for using the coupon is greater than 25 minutes)
* direction_same:0, 1 (feature meaning: whether the restaurant/bar is in the same direction as your current destination)
* direction_opp:1, 0 (feature meaning: whether the restaurant/bar is in the same direction as your current destination)
* Y:1, 0 (whether the coupon is accepted)
<br>


## Data Cleanup

* The Y column, which indicates whether or not the coupon was accepted, was cleaned by removing any rows where this field had no data.
* The 'passanger' column was renamed to correct the type to 'passenger'
* Any numeric values that did not contain data were replaced with the median value for the column
* Categorical columns were identified and printed to ensure values were as expected for the category
* Categorical columns with no value were filled in with the mode value for the column in question.
* I decided to forego converting categorical columns to numeric values representing the categories, as I did not find it as helpful as I had initially believed.
* The 'Y-Decoded' column was created to represent 'Accepted' (1) or 'Not Accepted' (0) as it is more readable than 1 or 0 as presented in the original 'Y' column. This enables the generation of more readable plots.

## General Findings

* Initial reviews of acceptance ratios based on gender proved to be about an even distribution between both Male and Female
* Direction information yielded to real data to analyze
* Coffee shops have the most significant level of coupon acceptance among those with some college education, but fall off for those attending graduate programs.
* It can be observed that those with higher incomes are not attracted to the idea of coupons that can be used as they travel from one place to another.
* Although it can be seen that their travel destination does affect coupon acceptance (those with no urgent place to go accept the coupon more frequently), it is essential to note that the hours before and after the commute appear to have more coupons accepted.
* Males travelling alone are a prime opportunity if their income is under $75k and they are travelling alone.

## Opportunities

* Although the data gathered is intended for a population of drivers, it is vital to take into account pedestrian opportunities.
* Pedestrian traffic on the weekends is likely to provide greater coupon acceptance when people are looking for a place to go.
* Restricting to only drivers is limiting the audience artificially.
* There is no data in the observations regarding the day of the week. As can be seen from the data, those who are not in a hurry are more likely to accept the coupon. Identifying the day of the week will confirm the assumption that a lack of urgency creates an opportunity for coupon acceptance.
