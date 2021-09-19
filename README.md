# kickstarter-analysis
Performing analysis on Kickstarter data to uncover trends 

## Overview of Project

### Purpose
In this analysis, we are attempting to make a recommendation about the best time to launch a Kickstarter campaign and what the goal amount should be for the campaign. This recommendation is based on data on outcomes for a variety of Kickstarter campaigns over the last couple years. We specifically focused on the data from fundraising campaigns for theater and play projects in our charts, though other data from other campaigns was also considered in our analysis.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
In our analysis of Outcomes Based on Launch date, first we wanted to filter our data to only include relevant theater campaigns.  After creating a filter for all columns in our data set, I separated the data into parent categories based on the general purpose of the campaign, then further into subcategories based on more specific criteria. I also filtered the data based on their outcome, i.e., was the campaign successful, failed, canceled, or currently live? Since we only want to evaluate campaigns that have been completed, we eliminated any campaigns that were currently active when the data was pulled. Once our data was filtered to just show the Theater campaign, we made a count of the completed theater Kickstarters that were successful, failed, or canceled. 

In order to compare the outcomes based on their launch dates, we needed to first translate the raw data for the launch date that was in terms of the Epoch/Unix Timestamp, into a more readable date. To do this we used the formula "=((("cell#ofUnixCode"/60)/60)/24)+DATE(1970,1,1)" which converted the timestamp into a month/day/year format for when the campaigns were launched. We also converted the end date of the campaigns using this same formula. 

We took these data and put them into a Pivot table where we further broke down what month the campaign was launched to see if there were any trends for success based on month of the year that a campaign was launched. After What we found is that there appears to be some correlation between the launch month and its success or failure. The most successful campaigns were launched in May, June, and July, with some slightly less successful campaigns in April and August. There does not appear to be a relationship between launch month and the failed or canceled campaigns since the data is relatively flat on the line graph. ![Theater Outcomes vs. Launch](/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
We also evaluated the outcomes of all Play Kickstarter campaigns based on the goal amount they set. This was to see if there were any Goals ranges that had more success or failure compared to others. In order to get an accurate view of the data, first we needed to separate our date into uniform ranges based on the goal amounts. Here we used the following ranges:
 ![Goal Range Values](/GoalRanges.png)
In a new sheet in Excel, we created a chart for the number of successful, failed, and canceled play campaigns in each of the goal amount ranges. The formula we used for this analysis was "=COUNTIFS(Kickstarter!$D:$D, ">=1000",Kickstarter!$D:$D,"<=4999", Kickstarter!$F:$F, "Successful", Kickstarter!$R:$R, "plays"). This formula means that we are counting the number of values in that meet the "if, then" criteria that was given. In this case, the first criteria is that the goal amount of the campaign is greater than, or equal to $1000, and less than, or equal to $4999. The second criteria is that the campaign is "successful" and last it must be in the "play" subcategory. We repeated variations on this formula for all of the goal ranges. Then repeated the analysis for the "failed" and "canceled" plays in the Kickstarter list. 

Once all plays had been sorted by goal amount and outcome, we calculated the percentage of the "successful", "failed", and "canceled" plays in each goal range. This was done by taking the number of plays with a given outcome in a range and dividing by the total number of plays in that range (For this I used the formula "=IFERROR(ROUND(((B2/E2)*100), 1), 0)" this rounded the value to the first decimal place and made any values divided by 0 become 0 instead of an error). The result of these analyses was this chart.
![Goals vs. Outcomes Chart](/Goals_vs_Outcomes_Chart.png)

In order to make this data more easily accessible visually, I created a line chart to show the percentage of each outcome broken down by the goal amount. 
![Outcomes by Goal](/Outcomes_vs_Goals.png)



### Challenges and Difficulties Encountered
I ran into a few challenges while completing this challenge. First, I had some issues with the details of some of the formulas. For example, I had issues with the =IFS( ) formula with the use of parentheses and commas. I had to look it up and do a bit or trial and error with my equations before I was able to get the equation to work. I have not worked in Excel extensively, so the syntax of the formulas was tripping me up. It became easier once I had done it more and understood the purpose for each part of the formula. 
I also had completed the entire Outcomes vs. Goals chart and had started the line chart before I realized that I had accidentally used the "Pledged" column amount for the first criteria in the =IFS( ) formula instead of the "Goal" amount column, which was what we needed. I had to go back and redo each of the formulas in the cells by hand, which was great additional practice for the =IFS ( ) formula! 

Another Challenge I encountered was when I was making the Pivot Chart from the Pivot Table and needed to get to have my rows in terms of months. I tried all kinds of combinations of variables after doing some google searches for help. I was finally able to have "months" show up as an option under the rows option. I am still not entirely sure what I did, but think it was using the years and the date created at the same time. Either way, I feel more confident in my ability to work through issues after completing this challenge. I had several times where I was trudging my way through and coming up with error after error, but I was able to work through it and come to the correct outcome, which feels great!


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
