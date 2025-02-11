# Pwc Power BI Internship

# Task1 - Call Centre Dashboard


## Problem Statement

This Call Center Dashboard is designed to provide insights into key performance metrics, helping managers monitor and optimize call center operations. This dashboard leverages Power BI / Tableau / Excel to visualize data effectively, enabling data-driven decision-making.

There are Key components of the dashboard which listed below:
1. Overall Call performance Summary
2. Total calls, Calls answered, Call abondoned,Calls resolved
3. Aveage speed of answer.
4. Agentwise filter
5. Various charts


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present  
- Step 5 : In the report view, from Build--> select Card to display below KPI's.
      . Total Calls
      . Calls answered
      . Calls abandoned
      . Calls resolved
      . Calls unresolved
      . Average speed of answer
- Step 6 : Added a table view which explains monthly summary which have all the details about the calls, agents,topics and so on. 
- Step 7 : Added Gauge chart to display average satisfaction rate.
- Step 8 : Added scatter chart to add Agent satisfaction rate, by adding agent in x axis, and average satisfaction rating in Y-axis.
- Step 9 : A donut chart is also added to the report design area representing the number of calls resolved and unresolved. 
- Step 10 : Slicers also added in visual for Topicwise and Agentwise call details
- Step 11 : In the report view, Add Title, respective images for call details.
- Step 14 : Measures are created to display teh KPI's.

for creating new measures following DAX expression was written;
       
        Avg Satisfaction rate = 
        
        AVERAGEX('Sheet1', 'Sheet1'[Satisfaction rating])

     Calls Abandoned = CALCULATE(COUNTROWS(Sheet1),Sheet1[Answered (Y/N)] ="N")
     Calls Answered = CALCULATE(COUNTROWS(Sheet1),Sheet1[Answered (Y/N)] ="Y")
     Calls_Resolved = CALCULATE(COUNTROWS(Sheet1),Sheet1[Resolved] ="Y")
     Calls_UnResolved = CALCULATE(COUNTROWS(Sheet1),Sheet1[Resolved] ="N")   


# Insights

A single page report was created on Power BI Desktop & it was then uploaded to Pwc Power BI internship site of Forage.


 # Report Snapshot of Call Centre (Power BI DESKTOP)
 ![Image](https://github.com/user-attachments/assets/cac74984-bedd-4fc5-90d5-a4ee3c192433)

# Task2 - There are 3 Pages for Task3
1) Welcome Page: It will explain about the KPI details,Churn Dashboard and Customer Risk Analysis overview.

![Image](https://github.com/user-attachments/assets/6b854db3-04a2-440c-817b-7397e06f74c3)

#Task2 -Part1- Churn Analysis 
## Problem Statement

It involves analyzing customer churn for a business, often a telecom or subscription-based service. The goal is to use Power BI to gain insights into customer retention, identify key churn indicators, and provide actionable recommendations to reduce churn.

There are 3 sections:
1. Demographics
2. Customer Account Information
3. Services Customers signed for.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present  
- Step 5 : In the report view, from Build--> select Card to display below KPI's.
      . Customers at risk
      . Yearly Charges
      . Monthly charges
      . Admin Tickets
      . Tech Tickets 
- Step 6 : Added 3 panels for Demographic,Customer Account Information and Services customers signed for respectively. 
- Step 7 : In Demographic section,added donut chart to display the ratio of Male and Female churn ratio.
- Step 8 : Added 3 cards for % of churn rate of senior citizens,dependents,Partners.
- Step 9 : Add stalked bar chart for % of subscriptionwise churn rate. 
- Step 10 : In Customer Account Information section,added stalked bar chart to display the % of chun rate Vs Payment method.
- Step 11 : Added Pie chart to display churn rate Vs Paperless billing.
- Step 12 : Added stalked bar chart for % of churn rate Vs Contract.
- Step 13 : Added 2 cards for Avg. Total charges and Avg. monthly rate.
- Step 14 : In Services Customer Signed for section,added Multirow Card to display as below:
       . The % of chun rate by Phone Services.
       . The % of chun rate by Streaming TV.
       . The % of chun rate by Streaming Movie.
       . The % of chun rate by Divide Protection.
       . The % of chun rate by Online backup.
       . The % of chun rate by Online Security.
       . The % of chun rate by Tech Support.
- Step 15 : Added donut chart to display churn rate Vs Internet Service.
- Step 16 : Added 2 cards for % of churn rate by Multiple lines(Yes/No).
- Step 12 : In the report view, Add Title, respective images for call details.
- Step 14 : Measures are created to display the KPI's.

for creating new measures following DAX expression was written;
       
 % Dependents = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"))

 % of Senior Citizen = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"), 
CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"))

% Partner = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Churn]="Yes"),0)

%DevideProtection = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[DeviceProtection]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"))

%No Multiple Lines = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[MultipleLines]="No",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[Churn]="Yes",'01 Churn-Dataset'[MultipleLines]<>"No phone service"),0)

%OnlineBackup = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[OnlineBackup]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"),0)

%OnlineSecurity = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[OnlineSecurity]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"),0)

%PhoneServices = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[PhoneService]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"))

%StreamingMovie = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[StreamingMovies]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"),0)

%StreamingTV = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[StreamingTV]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"))

%TechSupport = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[TechSupport]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"),0)

%Yes Multiple Lines = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[MultipleLines]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[Churn]="Yes",'01 Churn-Dataset'[MultipleLines]<>"No phone service"),0)

Churn Rate = 
DIVIDE(
    CALCULATE(COUNT('01 Churn-Dataset'[customerID]), '01 Churn-Dataset'[Churn] = "Yes"),
    COUNT('01 Churn-Dataset'[customerID]),
    0
)

Churned Customers = CALCULATE(COUNT('01 Churn-Dataset'[customerID]), '01 Churn-Dataset'[Churn] = "Yes")



# Insights

A single page report was created on Power BI Desktop & it was then uploaded to Pwc Power BI internship site of Forage.


 # Report Snapshot for Churn Analysis (Power BI DESKTOP)
![Image](https://github.com/user-attachments/assets/56b93410-630d-47bb-83f6-9c1d68b89864)

#Task2 -Part2- Customer Risk Analysis 
## Problem Statement

It typically involves analyzing customer data to assess potential churn risk. The goal is to use Power BI to visualize key risk indicators and provide insights that help businesses mitigate risks effectively.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present  
- Step 5 : In the report view, from Build--> select Card to display below KPI's.
      . Total Customers
      . Churn rate
      . Yearly charges
      . Admin Tickets
      . Tech Tickets 
- Step 6 : Added Column chart for % of chrun by Type of Internet Services. 
- Step 7 : Added Pie chart for Customers by Type of Internet Services.
- Step 8 : Added Pie chart for % of chrun by Type of monthly charges(Tenures).
- Step 9 : Added Line and stalked column chart for % of chrun by Contract. 
- Step 10 : Added Line and stalked column chart for % of chrun by Years of Contract. 
- Step 11 : Added Line and stalked column chart for % of chrun by Payment method. 
- Step 12 : Added 4 slicers 
        . Risk of churn(Yes/No)
        . Months Prescribed
        . Internet Services
        . Contract Type
- Step 12 : In the report view, Add Title, respective images for call details.
- Step 14 : Measures are created to display the KPI's.

for creating new measures following DAX expression was written;
       
 % Dependents = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"))

 % of Senior Citizen = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"), 
CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"))

% Partner = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Churn]="Yes"),0)

%DevideProtection = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[DeviceProtection]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"))

%No Multiple Lines = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[MultipleLines]="No",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[Churn]="Yes",'01 Churn-Dataset'[MultipleLines]<>"No phone service"),0)

%OnlineBackup = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[OnlineBackup]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"),0)

%OnlineSecurity = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[OnlineSecurity]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"),0)

%PhoneServices = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[PhoneService]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"))

%StreamingMovie = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[StreamingMovies]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"),0)

%StreamingTV = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[StreamingTV]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"))

%TechSupport = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[TechSupport]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"),0)

%Yes Multiple Lines = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[MultipleLines]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[Churn]="Yes",'01 Churn-Dataset'[MultipleLines]<>"No phone service"),0)

# Insights

A single page report was created on Power BI Desktop & it was then uploaded to Pwc Power BI internship site of Forage.


 # Report Snapshot for Customer Risk Analysis (Power BI DESKTOP)
 ![Image](https://github.com/user-attachments/assets/4db0125f-fdef-4f62-a808-4daa52ecb337)


 # Task3 - Diversity and Inclusion Dashboard


## Problem Statement

This Dashboard is typically involves analyzing workforce diversity data to provide insights into inclusivity within an organization. The objective is to create a Power BI dashboard that visualizes diversity metrics, identifies gaps, and offers recommendations for fostering an inclusive workplace.

There are Key components of the dashboard which listed below:
1. Hiring rate based on Job level and gender
2. Promotions by gender
3. Turn over rate


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present  
- Step 5 : In the report view, added slicers for below:
      . Department
      . Job Level
      . Age Group
      . Region Group
      
- Step 6 : Added 3 sections:
       . KP1 Hiring
       . KP2 Promotions(this year)
       . KP3 Turnover Rate (FY20 leavers)
- Step 6 : In KP1 Hiring, Added stalked bar chart to display Genderwise Job level.
- Step 6 : Added Line and clustered column chart to display % Job rate of Female employees by Job level.
- Step 9 : Added 2 cards for % of male and female.
- Step 10 :  In KP2 Promotions, Added Line and clustered column chart for % Female employees promoted in current year by job level.
- Step 11 : Added Clustered bar chart for %  of male female employees promoted in current year by job level.
- Step 12 :  In KP3 ProTurnover rate (FY20 leavers), Added line chart for comparison of FY20 Leavers or not.
- Step 13 : In the report view, Add Title, respective images for call details.
- Step 14 : Measures are created to display the KPI's.

for creating new measures following DAX expression was written;
       
 Avg Female Rating = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female"))

 Avg Men Rating = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male"))

 %Female = DIVIDE('Pharma Group AG'[Number of Female],'Pharma Group AG'[Number of Female]+'Pharma Group AG'[Number of Male])

 %Male = DIVIDE('Pharma Group AG'[Number of Male],'Pharma Group AG'[Number of Female]+'Pharma Group AG'[Number of Male])


# Insights

A single page report was created on Power BI Desktop & it was then uploaded to Pwc Power BI internship site of Forage.


 # Report Snapshot of Diversity & Inclusion (Power BI DESKTOP)
![Image](https://github.com/user-attachments/assets/d37f9774-8dda-42b5-a28c-310b81a46ee4)

 
