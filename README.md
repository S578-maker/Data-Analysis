# Pwc Power BI Internship-Call Centre Dashboard


## Problem Statement

This Call Center Dashboard is designed to provide insights into key performance metrics, helping managers monitor and optimize call center operations. This dashboard leverages Power BI / Tableau / Excel to visualize data effectively, enabling data-driven decision-making.

There are Key components of teh dashboard which listed below:
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
      .Average speed of answer
- Step 6 : Add a table view which explains monthly summary which have all the details about the calls, agents,topics and so on. 
- Step 7 : Add Gauge chart to display average satisfaction rate.
- Step 8 : Add scatter chart to add Agent satisfaction rate, by adding agent in x axis, and average satisfaction rating in Y-axis.
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


 # Report Snapshot (Power BI DESKTOP)
 ![Image](https://github.com/user-attachments/assets/cac74984-bedd-4fc5-90d5-a4ee3c192433)
 
