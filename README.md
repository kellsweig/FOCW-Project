# FOCW-Project


# Project Goals
The goal of this project is to utilize a combination of predictive modeling through maching learning and data analysis techniques to provide meaningful insights to the organization Friends of the Cobbossee Watershed (FOCW). FOCW is currently planning their 2024 budget and determining what base pay scale to hire employees at as the minimum wage in Maine increases. The organization would like to determine how much costs would increase at different pay rates as they may look to further increase their minimum pay to be competitive with other businesses. 

(say something about the other types of data and the purpose of predictive modeling? Do i have time to download and bring in the other data from other organizations?)

# Background
Friends of the Cobbossee Watershed (FOCW) is an environmental nonprofit in __ Maine
- Mission:
- Point Source Pollution and spread of invasive species
Organization Link: https://watershedfriends.com/


## Courtesy Boat Inspection (CBI) Program



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


# Developing a Model to Predict Total Inspections

# Forecasting 2024 budget 
FOCW requested budget forecasts for multiple What-If scenarios. First, they were interested in projections for how much the cost of labor would increase as wage increases. Second, they were interested in projections of the increase in cost if more shifts were covered in 2024 compared with 2023. 
- $15.50 average wage
- $16.00 average wage
- $16.50 average wage
- $17.00 average wage




