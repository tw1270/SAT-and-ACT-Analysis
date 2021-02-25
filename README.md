# Project 1: SAT & ACT Analysis
Tenzin Wangdu | 2.22.2021

### Problem Statement
---
In order to raise the participation rate for both exam, the college board want to figure out where to allocate their resources to increase the test takers. The participation rate and state required test taking data will help to find where to focus their resources on.


### Table of Contents
---
- [Data Collection](#Data_Collection)
- [Data Dictionary](#Data_Dictionary)
- [Data Import & Cleaning](#Data_Import_&_Cleaning)
- [Exploratory Data Analysis](#Exploratory_Data_Analysis)
- [Data Visualization](#Data_Visualization)
- [Conclusions and Recommendations](#Conclusions_and_Recommendations)
- [Soruces](#Sources)


### Data_Collection
---
Data is from the act and sat scores from 2019. It contains participation rate in each state and score of each section with total score. Also, I collected data from https://blog.prepscholar.com/which-states-require-the-sat for the sat and act requirement by state.

### Datasets
- [2019 Act Scores](../data/act_2019.csv)
- [2019 Sat Scores](../data/sat_2019.csv)
- [Sat & Act Requirement](../data/state_requirement.xlsx)

### Data_Import_&_Cleaning
---
Start off cleaning with checking for missing values and obvious issues with the observations. There are no participation rate in Puerto Rico and Virgin Islands. So, I remove them using pandas.datafrane.drop() to remove them because they have no values in the participation rate and there are territory not state. Also, I look at data types, and fix participation rate to float from object in both act and sat 2019 datasets. I use .rename() to make all the column lower case and .str.replace(' ','_') to remove spaces to _.

### Data_Dictionary

Now that, the data is clean and processed, let's create a data dictionary
A data dictionary provides a quick overview of features/variables/columns, alongside data types and descriptions. The more descriptive you can be, the more useful this document is.

For sat_2019_df

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|**object**|sat_2019|State in the U.S.A|
|**participation_rate**|*float*|sat_2019|The percent of participation of the Sat in each state.|
|**english**|*int*|sat_2019|The average score of each state in english part|
|**math**|*int*|sat_2019|The average score of each state in math part|
|**total**|*int*|sat_2019|The average score of each state in total|

For act_2019_df

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|**object**|act_2019|State in the U.S.A|
|**participation_rate**|*float*|act_2019|The percent of participation of the Act in each state.|
|**composite**|*float*|act_2019|The average score of all Act combine|

For state_req

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|**object**|state_req|State in the U.S.A|
|**sat_req**|**object**|state_req|Yes if the state requires the Test|
|**act_req**|**object**|state_req|Yes if the state requires the Test|

### Exploratory_Data_Analysis
---
The summary statistics of the data is a lot of states don't require the test. 23 states don't require any test to be taken. They are only 4 states above the 50 participation rate in both test. Florida, Hawaii, North Carolina, and South Carolina are the best case scenario where the state takes both. The Worst Scenario where the state have participation rate below 52% in both test; Oregon and Alaska have both no require to take the test.

Highest Participation Rate By State
- ACT: Alabama, Kentucky, Wyoming, Wisconsin, Utah, Tennessee
- SAT: Michigan, Colorado, Connecticut, Delaware, Florida, Idaho, Illinois, Rhode Island

Lowest Participation Rate by State
- ACT: Maine, Rhode Island, Delaware, New Hampshire, Pennsylvania, Michigan, Vermont, Massachusetts, Virginia, Connecticut
- SAT: North Dakota, Wyoming, South Dakota, Nebraska, Wisconsin, Mississippi

### Data_Visualization
---
Top 15 State in Sat participation
![alt text](https://github.com/tw1270/SAT-and-ACT-Analysis/blob/main/Image/top_15_sat_participation_state.png)

This shows the Act Participation throughout the state(the darker the red more participation)
<img src="https://github.com/tw1270/SAT-and-ACT-Analysis/blob/main/Image/Act%20Participation.png" style="float: left; margin: 20px; height: 55px">

State with both test Participation above 50%
<img src="https://github.com/tw1270/SAT-and-ACT-Analysis/blob/main/Image/state_above_50.png" style="float: left; margin: 20px; height: 55px">

State with both test Participation below 52%

<img src="https://github.com/tw1270/SAT-and-ACT-Analysis/blob/main/Image/state_belove_53.png" style="float: left; margin: 20px; height: 55px">


### Conclusions_and_Recommendations
---
Based on the exploration of the data, the key takeaways are less than half of the state are require to take both tests. You can increase the participation in Oregon by mandating the tests by district with free tests. Also another recommendation would be to have Sat or Act weekday tests for student who have worked and obligations on weekdays

### Sources:
---
* State Test Requirements: https://www.testive.com/state-sat-act/
* Oregon Extra Research: https://www.oregonlive.com/education/2020/03/oregons-public-universities-wont-ask-for-sat-scores-in-college-applications-anymore.html
* Alaska Extra Research: https://www.adn.com/alaska-news/education/2016/06/30/students-no-longer-need-national-tests-to-graduate/
