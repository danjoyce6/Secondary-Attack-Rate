# Secondary-Attack-Rate
Secondary attack rate for fevers using python

## Overview
The purpose of this analysis was to take fever data for a given dataset and calculate secondary attack rate by week and display that in a visualization.  The dataset given is deidentified health data with various demographics and fever temperatures for people across the country.  The data had to be cleaned and grouped appropriately and a visualization was created to display the results of secondary attack rate by week of the year to identify trends into fever.  There were some obvious peaks observed throughout the year that conincide with peaks from COVID-19 and flu.

## Resources
household_transmission_case.csv

## Tools Used
Python, Matplotlib, Pandas, Datetime

## Results
## 1.  Data Cleaning
The first thing that needed to be done to was to convert the 'yymmdd_index' into a datetime.  An anonymous function was called that changed it into a string and specified the format that we wanted the date to be in.  Then a week_num variable was created so that data could be displayed by week for the visualization.
![image](https://user-images.githubusercontent.com/88444529/160429046-8b21bd2f-d15b-4798-a294-23a0d9998bc7.png)
![image](https://user-images.githubusercontent.com/88444529/160429067-fee5934d-e0fa-4812-9e1e-929116a4d5e7.png)
Then based on the CDC definition of fever, the dataframe was filtered for only the rows with fever of index cases that had a temperature of 38 degrees celcius or above. 
![image](https://user-images.githubusercontent.com/88444529/160429286-eabbb870-2fe4-4bcb-9bee-9121c42e7cd0.png)
Then the data was grouped by profile_id_index and datetime so that each event of fever was captured in the dataset to be displayed in the visualization.  A sum of the secondary transmission cases was used so that for each event the total secondary transmission cases for each event would be displayed.  Other relevant variables were kept in the groupby statement such as secondary tranmission which is the variable of interest.  Then the dataframe was grouped by week_num to be displayed in the visual.  ![image](https://user-images.githubusercontent.com/88444529/160429881-09be7b11-56ef-49ca-ac74-938dfc633d27.png)
Finally the secondary attack rate by week was calculated by taking the sum of secondary transmission cases and dividing them by the count of index cases of fever.  The calculation and dataframe are presented in the following image.
![image](https://user-images.githubusercontent.com/88444529/160430414-18683a60-140e-4ef9-9f28-c6db126632e9.png)
## 2.  Vizualization

## 3.  Analysis
