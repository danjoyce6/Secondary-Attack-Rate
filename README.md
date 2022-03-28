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
A visualization of secondary attack rate by week was made using matplotlib.  The secondary attack rate was expressed as a percentage and line graph on the secondary y axis while the secondary case sum was displayed as a bar graph on the primary y axis.  The x axis is represented by the week of the year for 2021.  Two objects were created that would hold each of the variables on their respective y axes.  
![image](https://user-images.githubusercontent.com/88444529/160432317-9e4e5dd9-eb52-474f-9e06-69271602940b.png)
![image](https://user-images.githubusercontent.com/88444529/160432357-2f13da73-d363-4a6a-8d7e-93615ab1e6d4.png)

## 3.  Analysis
There are are a couple of things to notice on the visualization.  The COVID-19 variant Omicron, was first identified in the United States on December 1, 2021 or week 49.  In the visualization it can be seen that this corresponded with a big increase in the coming weeks.  Flu typically peaks between December and February and in visuals provided by the CDC there was also a peak in Flu activity at the end of 2021 going into 2022, when there was a dramatic increase in the secondary attack rate and secondary cases.  These results appear to represent the nation as a whole althugh there are some limitations when considering the data source such as misrepresentation of the younger age groups (they had a higher burden of disease during the Omicron surge) and some states are much more represented than others.
![image](https://user-images.githubusercontent.com/88444529/160433525-5d377411-3d24-407f-89b0-2281f21532e6.png)
![image](https://user-images.githubusercontent.com/88444529/160433541-41c39ae9-fe9d-4a14-9332-0ed5ebbc2b8c.png)


## Conclusions
This analysis gives a view of an accurate view of respiratory disease burden and transmission for diseases such as flu and COVID-19 in the United States.  Some of the limitations of this study were the ages of the individuals in the dataset.  This dataset was heavily influenced by younger people, as the median and mean ages of each row in the dataset was much lower than that of a representative sample in the United States.  In addition, some states are much more represented and further analysis should focus on standardizing the age as well as the representation from each state.
