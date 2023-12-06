# Insights for The Friends of the Cobbossee Watershed

![Friends of The Cobbossee Watershed Alternative otter logo](images/FotCW-Otter-Horizontal-2022-RGB-1200px.png)

# Introduction
Friends of the Cobbossee Watershed (FOCW) is an environmental nonprofit dedicated to protecting Cobbossee Lake and the surrounding watershed district. FOCW is currently planning their 2024 budget and determining what to pay the seasonal summer employees as the minimum wage in Maine increases. The organization would like to determine how much labor costs would increase with different pay increases as they consider further increasing their minimum pay beyond the minimum wage in order to be competitive with other businesses.The goal of this project is to utilize a combination of predictive modeling through maching learning and data analysis techniques to provide meaningful insights to the nonprofit.

# Background
Friends of the Cobbossee Watershed (FOCW) is an environmental nonprofit dedicated to protecting Cobbossee Lake and the surrounding watershed district. The nonprofit's conservation work is focused into 2 missions: combating runoff pollution and controlling the spread of invasive species. 
Organization Website: https://watershedfriends.com/


## Courtesy Boat Inspection (CBI) Program
Boaters can spread invasive species from one body of water to another when plants (or other species) remain on a boat when it is removed from the water. CBI is part of FOCW’s effort to combat the existence and introduction of invasive species to the lakes and ponds of the Cobbossee Watershed. During a courtesy boat inspection, one of FOCW’s trained Courtesy Boat Inspectors check boats and equipment for aquatic plants and educate boaters on how to properly wash boats and equipment to prevent the spread of invasive species. 

<img src="images/CBI.jpeg" alt="Woman conducting courtesy boat inspection" width="400"/>

Over the past few years, FOCW has covered approximately 80% of the shifts it aimed to staff for it's CBI program. The organization's goal has been to staff 10 sites during every weekend from Memorial Day to Labor Day as well as holidays. The Friends of the Cobbossee Watershed staff do also cover some weekday non-holiday shifts and volunteer trained inspectors also have covered some shifts though most shifts are staffed by paid inspectors. 

# Project Goals
1. Develop a model than can predict the number of inspections that would be conducted on a given shift
2. Use this model to project the total number of inspections in 2024 based on different scenarios
3. Create projections of both labor costs and the number of inspections for multiple scenarios
4. Identify times and locations to focus on when increasing shift coverage in order to maximize the number of inspections/ cost


# Data Dictionary
|Feature|Type|Description|
|---|---|---|
|SITE_NAME|object|The name of the site the inspector is based at| 
|DATE1|object|Date as an object variable| 
|DAY_OF_WEEK|object|The Day of the Week| 
|INSPECTOR_ID|int|The unique identifier of the inspector| 
|PAY_VOL|int|0 if volunteer, 1 if paid employee| 
|SHIFT_START|object|Time the shift began| 
|SHIFT_END|object|Time the shift ended| 
|TOTALINSP|float|The number of inspections conducted during the shift| 
|NUMINVASIVE|float|The number of invasive species found during the shift| 
|TOWN|object|The name of the town| 
|WATERBODY|object|The name of the waterbody the inspector is stationed at| 
|SHIFT_LENGTH|float|The length of the shift in minutes| 
|DATE|object|The date reformatted as date-time variable| 
|month|int|The month| 
|year|int|The year| 


# Data Cleaning & EDA
The 2023 CBI shift data was downloaded as a csv from a dashboard maintained by the Maine Department of Environmental Protection found at this link: https://maine.maps.arcgis.com/apps/dashboards/de2b7d59cab1437187eb49ac26f1d852. Data for 2021 and 2022 is not publicly available to be downloaded so initially this data was scraped using the code found in the Webscraping notebook in the Scratchwork folder. However, the data coordinator then sent over csv files with the 2021 and 2022 data which contained more variables than in the scraped data. Therefore, from that point the csv files provided by the Department of Environmental Protection were used for EDA and modeling. ]

### Initial Data Cleaning
The names of the inspectors aren't necessary and were dropped to preserve employee privacy. The number of invasive species identified, the number of motorized vehicles, and the number of non-motorized vehicles are all variables that would not be known before a shift begins. These variables are actually dependent on the number of inspections (the dependent variable in the model) rather than predictive of this variable and were all dropped as well. Comments, IDs of the site, and longitutde/ latitude are all redundant with the site_name and were also dropped. The only other significant data cleaning steps were to match variable and value names from 2022 to 2023 as the names in the datasets changed during that times. All Data Cleaning steps were conducted in the Data Cleaning and Feature Engineering notebook.

### EDA Findings
The most notable findings during the initial exploration of the data were that none of the numeric variables were highly correlated with the total number of inspections but that there were significant trends related to the location (site) of the shift and the time of day (day_part) when the shift began. Given the general lack of significant relationships, I believed that the most successful models would only be able to account for some of the variation in the total number of inspections per shift.

# Feature Engineering
#### Capturing impact of time of day
Goal: Create columns for the part of the day when a shift starts and ends
#### Handling Inspector_ID:
- Some inspectors are more experienced than others, returning from prior years, working more shifts, and receiving higher pay
- According to the program coordinator, there were some issues in 2023 with inspectors not inspecting all present boats
- Goal: create a variable to capture the experience level of the inspector stationed for that shift

try to add in the holidays as another column, and then to use feature engineering with shift length, shift start and shift end to attempt to somehow capture time of day.

The models were all less overfit, however the tree models are still overfit. Parameter optimization could help reduce the overfit as well to balance out the metrics of the tree based models between the training and test scores. 

# Developing a Model to Predict Total Inspections



# Deploying the Model to Create Projections
I deployed the model on multiple what-if scenarios to gain insights into how to optimize the process of increasing shift coverage. I created these scenarios by examining shifts that were not covered in 2023. In each scenario I simulated covering 100 extra shifts. In the first scenario, all shift variables were filled randomly based on the proportions of values in the original dataset and then merged with the weather data for that date. In the second scenario, start time was set to be 7 am for a 4 hour shift. In the third scenario, the start time remained the same but for an 8 hour shift. In the fourth scenario, I simulated 8 hour shifts that begin at 9:30 (the mean start_time in the 2023 data). 

### Scenario Creation Process
1. Identify shifts that were not covered in 2023
2. Create a dataset of just the uncovered shifts
3. Develop each step of the process of filling this data (merging with weather, setting start times, feature engineering)
4. Create a function to fill in the values of each scenario

### Prediction Process
1. Use the pickled model to predict values for the what-if scenarios
2. Sum the predictions
3. Use bootstrapping to create a prediction_interval (95%)


# Results

# Conclusion

# Reccommendations
- Encourage volunteers to sign up for earlier shifts- and don’t discourage short targeted shifts!
- Focus on staffing the higher volume boat launches first
- Expand weekday shifts when possible
- Increase the base pay rate to hire more staff and cover more shifts
    - Can consider offsetting the costs by decreasing shift lengths


# Next Steps

