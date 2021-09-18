# Readme for homework3 question2

## Instruction

This readme file contains:

1)Explanation on the process of data processing.

2)Discussion on any steps in the process (or processing the data in general) that could potentially lead to errors in reporting.

3)Answer of bonus question.


## Support
If you have any question, please feel free to [contact me](https://github.com/QingyangYu0529/BIS-633-QingyangYu#Maintainer).

Any comments or insights would be greatly appreciated.


## Question 2

### Data processing

1)All codes written in python. Code files are .ipynv format.

First I imported library pandas to load dataset "BRFSS_19_data.csv".

2)Then I checked the [LLCP 2019 Codebook Report document of the Behavioral Risk Factor Surveillance System](https://www.cdc.gov/brfss/annual_data/2019/pdf/codebook19_llcp-v2-508.HTML). I found that the FIPS code of state Connecticut is 09. I filtered the data to include only respondents in the state of Connecticut, the result was saved into the list data_CT.

<img src="https://github.com/QingyangYu0529/BIS-633-QingyangYu/blob/main/Figures-in-running-result/data_state_Connecticut.jpg" style="zoom:150%;" />


3)According to the [LLCP 2019 Codebook Report document of the Behavioral Risk Factor Surveillance System](https://www.cdc.gov/brfss/annual_data/2019/pdf/codebook19_llcp-v2-508.HTML), I found that the variable 'EXRACT11' refers to the type of physical activity reported by respondents. I selected 'Jogging' among the exercise activities listed for variable EXRACT11, which is represented by value 28.

So I filtered the data in which the value of column 'EXRACT11' is 28, in order to select all the people that spend the most time to jog. The result was saved into the list data_jogging.

<img src="https://github.com/QingyangYu0529/BIS-633-QingyangYu/blob/main/Figures-in-running-result/data_jogging.jpg" style="zoom:150%;" />

According to the [LLCP 2019 Codebook Report document of the Behavioral Risk Factor Surveillance System](https://www.cdc.gov/brfss/annual_data/2019/pdf/codebook19_llcp-v2-508.HTML), I found that variable '_SEX' refers to the sex of each respondent: value 1 refers to male, and value 2 refers to female. 

Then I used groupby to group all the people that favourite jogging by gender, the result was saved into the list data_jogging_by_sex.

<img src="https://github.com/QingyangYu0529/BIS-633-QingyangYu/blob/main/Figures-in-running-result/data_jogging_by_sex.jpg" style="zoom:120%;" />

> According to the running result, number of male respondents who selected the activity 'Jogging' is 1439. While number of female respondents who selected the activity 'Jogging' is 832.


### Bonus Question

According to the [LLCP 2019 Codebook Report document of the Behavioral Risk Factor Surveillance System](https://www.cdc.gov/brfss/annual_data/2019/pdf/codebook19_llcp-v2-508.HTML), I found that variable 'HTIN4' refers to the reported height in inches.

Noted that there are two circumstances:
If the value of HTIN4 is 36-95, the unit of reported height is (inches).

If the value of HTIN4 is BLANK('NaN'), respondent do not know/refused/was not asked to answer about their heights, or the reported height is missing.

First, I removed all the 'NaN' from dataframe data_CT, the result was saved into the list data_CT_height. 

Then I extracted the column 'HTIN4', the result was saved into the list data_CT_height.

<img src="https://github.com/QingyangYu0529/BIS-633-QingyangYu/blob/main/Figures-in-running-result/data_CT_height.jpg" style="zoom:120%;" />

To get the average height of people living in Connecticut, I calculated the average height(unit: inch), then transferred the unit into meters, and printed the result.

<img src="https://github.com/QingyangYu0529/BIS-633-QingyangYu/blob/main/Figures-in-running-result/print_result_avg_height.jpg" style="zoom:120%;" />


### Discussion on potential errors

1) We need to understand the data before data analysis! 

In most of the cases, the details about data are in the notebook/codebook, which is also provided on the website.

Before data processing, it is important to know the meaning of each column in BRFS File, which could be found in the [LLCP 2019 Codebook Report document of the Behavioral Risk Factor Surveillance System](https://www.cdc.gov/brfss/annual_data/2019/pdf/codebook19_llcp-v2-508.HTML).

2) Always choose the data that is easier to manage!

Compared with the column 'HEIGHT3', column 'HTIN4' and 'HTM4' has fewer types of values, which means they are easier to be analyzed.

3) Be careful about the object to be analyzed!

Which part of the data is considered? Which part of the data should be eliminated? Errors may occur if we do not think of these questions.

For instance, when I am asked to provide the number of male and female respondents who selected that same activity, I first used the data from the last step, which includes only respondents in the state of Connecticut. Then I realized these two questions are parallel, and I should use the whole data.

4) Be careful about the details of the data!

When I calculated the average height for a person in the Connecticut, it is rather important to know the unit of the data placed in that column, and to remove the blank value before calculation.





## Data source

Data of homework 4 question 2 comes from [BRFS File](https://yale.instructure.com/courses/70309/files/5377487/download).


All details about data comes from [LLCP 2019 Codebook Report document of the Behavioral Risk Factor Surveillance System](https://www.cdc.gov/brfss/annual_data/2019/pdf/codebook19_llcp-v2-508.HTML)

## Maintainer
@QingyangYu0529
| Name        | Email                | Organization                                                 |
| :---------: | ---------------------| ------------------------------------------------------------ |
| Qingyang Yu | qingyang.yu@yale.edu | Graduate student, Yale School of Public Health, Yale University |