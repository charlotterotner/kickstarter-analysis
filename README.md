# Kickstarting with Excel

## Overview of Project

### Purpose
The purpose of this analysis was to provide Louise with recommendations for her kickstarter campaign based off historical kickstarter data. We want to ensure her project will be set up for success based off her budget, type of kickstarter, and other criteria. We know that Louise’s campaign is going to be a play so I focused most of my analysis on plays. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
For theater outcomes based on launch date I started by converting our Unix time stamps to a readable format so we could easily read the start and end date of each campaign.  To do this I used the formula `=(((J2/60)/60)/24)+DATE(1970,1,1)`.
Once I had the date in a readable format I created a pivot table and then a line graph so I could easily see the outcome amounts for theater kickstarters over the different months of the year. Below is the graph I created. 

![image description or alt text](https://raw.githubusercontent.com/charlotterotner/kickstarter-analysis/main/Resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
To conduct the anlaysis of outcomes based on goals I first created the goal ranges. To then find the amount of successes, failures, and cancels for each range I used a COUNTIF function. I note this below in my challenges, but to make things a bit easier and less prone to error I split up the ranges into two different columns and then used varitaions of the following formula: 
`=COUNTIFS(Kickstarter!$D:$D,">"&A3,Kickstarter!$D:$D,"<="&B3,Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")`

Once I had the count for each category for each range I calculated the total projects using the SUM function and then found percentage successful and percentage failed by simply dividing the amounts in each category by the total I found using the SUM function. 

Below is the graph I created: ![image description or alt text](https://raw.githubusercontent.com/charlotterotner/kickstarter-analysis/main/Resources/Outcomes_vs_Goals.png) 

### Challenges and Difficulties Encountered
I came across a bit of a challenge while creating the last graph. Inputting the ranges and using the recommended formula meant hardcoding the goal amounts into the formula. The first go around I made an error and added one too many zeros in a couple places causing my graph to look off. To correct this and make this a bit easier on myself a colleague recommended splitting the ranges into two columns so hard coding was not necessary and I could copy and paste the formulas more easily. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

For theater outcomes based on launch date it appears that, historically, there are more successful theater kickstarters that launch in the early summer. In the months of May, June, and July, we saw the greatest volume of successes for theater campaigns. On the flipside, December has historically been the worst time of year to launch a kickstarter with the number of successes and failures being about equal. I'd recommend that Louise launch her kickstarter around the month of May.

We can also conclude that those summer months tend to be the most popular times to launch kickstarters since we also saw a slight spike in failures in the same summer months.

- What can you conclude about the Outcomes based on Goals?

Overall, it seems that kickstarters with a lower goal amount, specifically goal amounts under $5,000, tend to see the highest success rates at 70% or greater. That being said there aren’t very many kickstarter campaigns in the data set that had a goal over $25,000 (only 38 out of 978 play kickstarters) so we may not have enough data to know for sure if setting a higher goal has an impact on success. To be safe, Louise should probably set her goal around $5,000 or less. 

- What are some limitations of this dataset?

This dataset has a number of limitations. One is the fact that we have different currencies so goal and pledged amounts were not being compared equally across different currencies. We could do a currency conversion, but we wouldn’t have the accurate conversion from the time when that kickstarter was launched and it would be difficult to convert the currencies accurately. 

Another limitation is that we only have kickstarter data from 2009-2017. If Louise wants to launch her kickstarter campaign in 2022 it would probably be more beneficial for me to analyze more recent historical data. 

- What are some other possible tables and/or graphs that we could create?

I think graphing the percentage of successes based on launch date would be more helpful than overall volume of successes. I think we can probably assume there are more kickstarters launched in those early summer months which could potentially be part of the reason we saw a spike around that time. Additionally, it would be beneficial to create a chart using some of the data points we didn’t use in this analysis. For example, if the kickstarter was a "staff pick" or “spotlight” kickstarter. I was not provided background on what those categories entailed but creating a chart for success rates based off those categories could give Louise further insight on what criteria her kickstarter needs to fulfill in order to have the best chance of being successful.
