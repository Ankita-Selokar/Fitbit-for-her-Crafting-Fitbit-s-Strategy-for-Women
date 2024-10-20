# Fitbit for her: Crafting Fitbit's Strategy for Women

## Scenario:
### 1. Case Study:   
Welcome to the "Fitbit for Her: Crafting Fitbit's Strategy for Women" data analysis case study! In this project, you will take on the role of a junior data analyst, tasked with performing real-world analysis to help Fitbit by Google strengthen its market presence among female customers.

### 2. Company: 
Google is a multinational technology company known for its search engine, which is one of the most widely used globally. Founded in 1998 by Larry Page and Sergey Brin, it has since expanded into various areas such as online advertising (Google Ads), cloud computing (Google Cloud), software (Android OS, Google Chrome), and hardware (Pixel devices). Google also owns platforms like YouTube and offers a wide range of services, including Gmail, Google Maps, and Google Drive. It operates under its parent company, Alphabet Inc., and is a leader in artificial intelligence and machine learning technologies.

### 3. Product: 
Fitbit is a company that produces wearable fitness devices designed to track users' health and activity data, such as steps taken, heart rate, sleep patterns, and more. Founded in 2007. In January 2021, Fitbit was acquired by Google and absorbed into its hardware division. Google rebranded their Fitbit devices as "Fitbit by Google". Fitbit's products include smartwatches and fitness trackers that sync with an app, allowing users to monitor their physical activity, set fitness goals, and gain insights into their overall health. Fitbit has gained popularity for promoting a more active lifestyle Google further integrating its technology with health-focused services.

### 4. Problem Statement:
Fitbit seeks to enhance its market presence by effectively targeting female customers with new product offerings. The initial step involves identifying competitive brands in the smart device and fitness tracker market. Following this, the analysis will compare female customer data from these competitors with Fitbit's own female customer data to uncover insights and preferences. The final phase will involve a detailed examination of Fitbit's female customers to identify trends and patterns that can inform product features and marketing strategies for future launches.

## Data Analysis Phase: Case Study
The data analysis process consists of the phases, asking, preparing, processing, analysing, sharing, and acting. These are essential for deriving meaningful insights from data. By effectively moving through each stage, from formulating the right questions to implementing informed actions, you unlock the full potential of data. Following data analysis phases contains the details about this project.

### 1. Ask phase

#### Business Task
Fitbit by Google is set to launch a new product for women and has tasked you with analyzing smart device usage data. Your objectives include examining how consumers use non-Fitbit smart devices and analyzing insights from Fitbit's female customers to identify trends and preferences. Synthesize these findings into actionable insights and prepare a presentation to inform product development and marketing strategies for the new offering. Your analysis will help ensure the product resonates with female consumers and strengthens Fitbit's market position.

Following three points are the questions needed to be answered by this analysis.
1. 1. Which fitness tracker brand dominated the market in the last quarter, and how did Fitbit's performance compare to the top competitors in terms of sales and customer satisfaction?
2. What are some trends in smart device usage?
3. How could these trends apply to Fitbit customers?
4. How could these trends help influence Fitbit marketing strategy?

### 2. Prepare phase

#### Data Sets Used: 
I. To find the competitors brands the Ecommerce Data set was used from kaggle 
(https://www.kaggle.com/datasets/devsubhash/fitness-trackers-products-ecommerce)
II. Apple vs Fitbit dataset was downloaded from Harvard Dataverse
(https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/ZS2Z2J)
III. Fitbit data was available on kaggle
(https://www.kaggle.com/datasets/arashnic/fitbit)
Meta data:
Total Data sets: 3
Source: kaggle, Harvard Dataverse
File Type: CSV
Tools for Analysis: Spreadsheet, Excel, BigQuery.
Visualisation Tool: Power BI, Looker Studio

### 3. Process phase 

For my analysis I decided to look at the following datasets:
Top_Fitness_trackers
apple_fitbit_data
dailyActivity_merged
sleepDay_merged
dailyCalories_merged
dailySteps_merged
hourlyCalories_merged
hourlySteps_merged

#### Excel Process to Clean Data:

I used Excel to clean each dataset, here are the following steps needed for each dataset:

##### Top_Fitness_trackers
* Eliminated duplicate entries and empty rows.
* Removed unnecessary columns.
* Utilised pivot tables to identify the top-rated and best-selling brand.
##### Apple_fitbit_data
* Eliminated duplicate entries and empty rows.
* Separated the data by gender to create a new dataset containing only female entries.
* Applied oversampling to address the bias and balance the dataset.
* Split Activity Column to Group the Activity into 3 categories. 
##### dailyActivity_merged
* Eliminated duplicate entries.
* Excluded data where steps were below 2000, as this likely indicates the user didn’t wear the device for the full day or the battery ran out.
##### sleepDay_merged
* Removed the "AM" indicator from the sleepDay column as it was not relevant.
* Split the sleepDay column into separate Date and Time columns using the SPLIT function.
* Reformatted the TotalMinutesAsleep and TotalTimeInBed columns from whole numbers to the hh:mm format by dividing each value by 1440 (the total number of minutes in a day).
Applied the Remove Duplicates function to eliminate any duplicate records.
* Excluded outlier data by removing entries where Time in Bed exceeded 13 hours or was less than 3 hours to filter out naps or inactivity.
##### dailyCalories_merged
* Removed calories counted below 600 as a result this low could be due to improper use of the device.
##### dailySteps_merged
* Removed steps counted below 2000 as this would most likely be the result of the user not wearing the device for the entire day or the battery dying.
##### hourlyCalories_merged
* Eliminated duplicate entries.
* Separated date into day and time using the SPLIT function.
* Excluded blank time entries to focus on analysing the time of day when users burned the most calories.

### 4. Analyze 

After cleaning the datasets, I chose to conduct the analysis using SQL in BigQuery, linking the query output tables to a spreadsheet for visual exploration. While the datasets could have been managed in Excel, I leveraged this opportunity to sharpen my SQL skills and treat this case study as a valuable learning experience. For Business Task 1, I utilised Power BI to visualise key data insights, demonstrating my proficiency in data visualisation.

#### Power BI Analysis
* Analysed various fitness tracker brands and their customer ratings to identify the top-performing and most loved brand.
* Identified Apple as the top-rated brand, holding 46.71% of the ratings with a perfect score of 5, compared to Fitbit's strong rating of 4.7.
* Analysed pricing trends, revealing that Apple has the highest selling price with the most customer ratings, while Fossil, despite a lower price than Fitbit, had the second-highest rating count.
* Conducted a gender-wise market distribution analysis, finding that while both Apple and Fitbit have similar results, Fitbit attracts a higher proportion of female customers than Apple.

#### SQL Upload 

​I uploaded the cleaned datasets to BigQuery to perform analysis. In some cases, I used Spreadsheet to create visuals.


```SQL

-- Total Number of Users:
SELECT COUNT(DISTINCT Id) as Total_users
FROM `market-analysis-fitbit.Fitbit_customer.DailyActivity`


```


### 									Thank You
