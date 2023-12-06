# Insights for The Friends of the Cobbossee Watershed

![Friends of The Cobbossee Watershed Alternative otter logo](images/FotCW-Otter-Horizontal-2022-RGB-1200px.png)

# Introduction
Friends of the Cobbossee Watershed (FOCW) is an environmental nonprofit dedicated to protecting Cobbossee Lake and the surrounding watershed district. FOCW is currently planning their 2024 budget and determining what to pay the seasonal summer employees as the minimum wage in Maine increases. The organization would like to determine how much labor costs would increase with different pay increases as they consider further increasing their minimum pay beyond the minimum wage in order to be competitive with other businesses.The goal of this project is to utilize a combination of predictive modeling through maching learning and data analysis techniques to provide meaningful insights to the nonprofit.

# Background
Friends of the Cobbossee Watershed (FOCW) is an environmental nonprofit dedicated to protecting Cobbossee Lake and the surrounding watershed district. The nonprofit's conservation work is focused into 2 missions: combating runoff pollution and controlling the spread of invasive species. 
Organization Link: https://watershedfriends.com/
- mission statement
- region (Cobbossee watershed area- how many lakes & ponds etc)
- organization structure (6 full time and then seasonal employees + volunteers)
- define any key terms

Explain the issues FOCW has had with hiring seasonal employees, being competitive with Dunkin Donuts and other minimum wage jobs

Transitioning to new leadership


## Courtesy Boat Inspection (CBI) Program
CBI is one of FOCW’s programs to combat the existence and introduction of invasive species to the lakes and ponds
FOCW’s trained Courtesy Boat Inspectors check boats and equipment for aquatic plants
Boaters can spread invasive species from one body of water to another when plants (or other species) remain on a boat when it is removed from the water
10 boat launches that FOCW staffs 



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
The 2023 CBI shift data was downloaded as a csv from a dashboard maintained by the Maine Department of Environmental Protection found at this link: https://maine.maps.arcgis.com/apps/dashboards/de2b7d59cab1437187eb49ac26f1d852. Data for 2021 and 2022 is not publicly available to be downloaded so initially this data was scraped using the code found in the Webscraping notebook in the Scratchwork folder. However, 


# Feature Engineering


# Developing a Model to Predict Total Inspections


# Budget Projections
FOCW requested budget forecasts for multiple What-If scenarios. First, they were interested in projections for how much the cost of labor would increase as wage increases. Second, they were interested in projections of the increase in cost if more shifts were covered in 2024 compared with 2023. 
- $15.50 average wage
- $16.00 average wage
- $16.50 average wage
- $17.00 average wage


# Conclusions/ Results


# Next Steps

