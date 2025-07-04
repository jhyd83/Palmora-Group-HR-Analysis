# The Palmora-Group-HR-Analysis
## Project Description
To analyse the company’s HR data and come up with recommendations for management’s attention with respect to gender equality in Palmoria
## Data Source
The dataset given was in Excel format from the CHRO of The Palmoria Group
## Tools used
The tool used for this work is the Power Query Editor in Power BI
 - For data collection
 - For data transformation
 - For Analysis
 - Visualizations for presentation
## Assumptions
 - Generally, there are two genders in the organization. However, some employees refused to disclose their gender. You would need to assign a generic gender status to these employees: These set of employees were represented with "Undisclosed" in the dataset
 - The location was assumed to be the company's regions and so was replaced with "Region"
 - Some employees are without a salary because they are no longer with the company. You will need to take those employees out: These were taken out
 - Lastly, some departments are indicated as “NULL”. These departments would also need to be taken out: These were taken out

## Introduction
The Palmoria Group is a manufacturing company based in Nigeria that has an embroided issues about gender inequality in its 3 regions where there businesses are located. Unfortunately, the media recently published in the news with the headline “Palmoria, the Manufacturing Patriarchy” this doesn’t look good to the owner of the business on their ambition to scale the business to other regions and even overseas.
This documentation outlines the data cleaning process for The Palmoria Group business. Three datasets were given to work on and to know about the issues the company is currently facing. The datasets are given below:
 - The bonus mapping & rules : These contain the rule for making payments to the employees in the company and their work rating
 - The Palmoria Group emp-data : This contains the employees details.

## Problem Statement
 - 1.	What is the gender distribution in the organization? Distil to regions and departments
 - 2.	Show insights on ratings based on gender
 - 3.	Analyse the company’s salary structure. Identify if there is a gender pay gap. If there is, identify the department and regions that should be the focus of management
 - 4.	A recent regulation was adopted which requires manufacturing companies to pay employees a minimum of $90,000
    - 	Does Palmoria meet this requirement?
    - 	Show the pay distribution of employees grouped by a band of $10,000. For example:How many employees fall into a band of $10,000 – $20,000, $20,000 – $30,000, etc.?
    -  Also visualize this by regions
 - 5.	Calculate the amount to be paid as bonus to individual employees
    - 	Calculate the total amount to be paid to individual employees (salary inclusive of bonus)
    - 	Total amount to be paid out per region and company-wide

  ## DATA Description
The Palmoria Group manufacturing company gave out a data set of 3 different tables which are the bonus mapping, bonus rules and The Palmoria Group emp-data. The bonus mapping and bonus rules consists of 12 rows and 6 columns while The Palmoria Group emp-data consists of 6 columns and 1015 rows. The Palmoria Group emp-data table contains a range of employees details such as Employees name, Gender, department, salary, location and rating, while the bonus rules and mappings which are the same consist of 12 rows and 6 columns consists of the department and the ratings ie very poor, poor, very good, good and average.

### Data Cleaning Process
Using the tools available in Power Query Editor, I was able to perform the following transformation to the data set:
#### Text Cleaning
One of the issues identified during the data cleaning process was with the “Gender” column. The column contains male, female and blank so I replaced the blank with Undisclosed. The power query replaced values was used
#### Department column
There are few rows that has a “NULL” text in the column so I removed it by unchecking it from the list of other department rows. Which reduced the rows to 987.
#### Salary Column
There are few rows that has a “null” text in the column so I removed it by unchecking it from the list of other salary rows. Which further reduced the rows to 946 rows
#### Salary band column
This was done using the "Add conditional column" where our condition statement was done by grouping each band into their various categories ..ie an IF statement ; For example; if [Salary] <= 20000 then “$10,000-$20,000” and so on in bands of $10,000) 
#### Merge table
I created a merge table to be able to get the employee who’s worthy of a bonus base on their performance rating so I was able to merge the Palmoria Group emp-data and the bonus rules table together. I merged them by joining their unique identifier which is the “Department” column so that gives me the bonus discount column 

## Analysis & Inferences
### Gender Distribution 
 - The gender disparity is most prominent in the Kaduna region (M-F ratio: 182–165), followed by Lagos (M-F ratio: 124–118) and then Abuja which has a negligible gender disparity (M-F ratio: 159–158).
 - Of the 12 departments, 7 have a higher Male headcount, with the Legal department leading the pack (M-F ratio: 49–34).
 - Overall, the gender disparity across the company is considered ‘MARGINAL’.
   
### Salary Structure
 - A gender pay gap exists across all regions of the company; at an average M-F salary ratio of $74.8k — $72.1k, male employees were noted to earn slightly more in all regions.
 - Male employees earned more in total terms across 7 departments. On the average, Male employees earned more in 9 departments across the company.
 - The Palmoria Group has 69%(654 employees) of their employees below the minimum salary threshold and the difference between the male and female number of employees below minimum salary is 2 showing a very marginal disparity
 - Given the marginal pay gap, there isn’t sufficient evidence based on available data to conclude if the disparity is reflective of patriarchy.

### Performance Ratings & Bonuses
 - Female employees overall performed better in the period under review (reflected in higher overall bonuses which accrued to females taking 48.34% of the total bonus payout).
 - The first two high bonus payments were also to the female gender.

## Conclusion/Recommendation
Given the minimal disparity in count and pay gap by gender, The Palmoria Group should consider reviewing its employment and remuneration policy to close the inherent gender gaps and neutralize current negative opinions. The Palmoria Group needs to review the salary structure across the company to meet the minimum wage requirement to avoid legal infraction. The company should also reveiew thier information/communication disclosure policy in order to give out more appropriate information to the public to guide against misinformation. 










