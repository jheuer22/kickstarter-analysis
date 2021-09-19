# kickstarter-analysis
Performing analysis on kickstarter data to uncover trends 
## Overview of Project

### Purpose
In this analysis, we are attempting to make a recommendation about the best time to launch a Kickstarter campaign and what the goal amount should be for the campaign. This recommendation is based on data on outcomes for a variety of Kickstarter campaigns over the last couple years. We specifically focused on the data from fundraising campaigns for theater and play projects in our charts, though other data from other campaigns was also considered in our analysis.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
In our analysis of Outcomes Based on Launch date, first we wanted to filter our data to only include relevant theater campaigns.  After creating a filter for all columns in our data set, I separated the data into parent categories based on the general purpose of the campaign, then further into subcategories based on more specific criteria. I also filtered the data based on their outcome, i.e., was the campaign successful, failed, canceled, or currently live? Since we only want to evaluate campaigns that have been completed, we eliminated any campaigns that were currently active when the data was pulled. Once our data was filtered to just show the Theater campaign, we made a count of the completed theater Kickstarters that were successful, failed, or canceled. 

In order to compare the outcomes based on their launch dates, we needed to first translate the raw data for the launch date that was in terms of the Epoch/Unix Timestamp, into a more readable date. To do this we used the formula "=((("cell#ofUnixCode"/60)/60)/24)+DATE(1970,1,1)" which converted the timestamp into a month/day/year format for when the campaigns were launched. We also converted the end date of the campaigns using this same formula. 

We took these data and put them into a Pivot table where we further broke down what month the campaign was launched to see if there were any trends for success based on month of the year that a campaign was launched. After What we found is that there appears to be some correlation between the launch month and its success or failure. The most successful campaigns were launched in May, June, and July, with some slightly less successful campaigns in April and August. There does not appear to be a relationship between launch month and the failed or canceled campaigns since the data is relatively flat on the line graph. ![Theater Outcomes vs. Launch](/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
We also evaluated the outcomes of Play Kickstarter campaings based on the goal amount they set. 

### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
