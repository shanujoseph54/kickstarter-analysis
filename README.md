# Analysis of Kickstarter Campaigns


## Overview of Project

This project analyzes Kickstarter data from 2009-2017 to help Louise figure out how to plan a successful Kickstarter campaign. The playwright is planning on launching her play, "Fever," in the United States with a budget of $10,000 and is hesitant about jumping into her first crowdfunding campaign. Kickstarter crowdfunding data is used as the research source for analysis and recommendations are provided to the playwright, regarding when to launch her campaign and how much money she should plan to fundraise. These findings are visually presented using charts and graphs to help Louise make quick decisions easily.

### Purpose

The purpose of this project is to analyze the Kickstarter campaign data to find trends and relation between attributes that contribute to a successful crowdfunding campaign. For this analysis, the focus will mainly be on how the goal amount and campaign launch date impacts a successful campaign.

## Analysis and Challenges

For analysis, I was provided with a worldwide list of Kickstarter campaigns categorized by outcomes, goal, country, category, launch date. The analysis here is focused on the parent category theater with subcategories: plays, musicals, and spaces. I have also used several advanced Excel formulas to organize, sort and deep dive into the data to better understand the relationships of the Kickstarter campaign data.

To determine how different campaigns fared in relation to their launch dates and funding goals, two main factors were analyzed:

1. Outcomes Based on Launch Date
2. Outcomes Based on Goals

### Analysis of Outcomes Based on Launch Date


![Theater_Outcomes_vs_Launch.png]( https://github.com/smj452/kickstarter-analysis/blob/master/resources/Theater_Outcomes_vs_Launch.png)

The above image categorizes successful, failed and canceled theater Kickstarter campaigns based on their launch date from 2009 through 2017. I extracted the date from the 'Date Created Conversion' field in the Kickstarter excel sheet. In total, there were 1,369 theater Kickstarter campaigns for the given date range. A pivot table was used to analyze total successful, failed, and canceled campaigns. Louise was curious to know if there were certain months that were more or less successful for starting a theatre campaign.

### Analysis of Outcomes Based on Goals

![ Outcomes_vs_Goals.png]( https://github.com/smj452/kickstarter-analysis/blob/master/resources/Outcomes_vs_Goals.png)

The above image depicts successful, failed and canceled Kickstarter plays based on the percentage of their funding goal that they obtained. Plays is a subcategory to the parent category theatre. For this analysis, I calculated the number of successful, failed and canceled plays that fell into designated ranges of funding goals on the Kickstarter worksheet. In total, there were 1,047 projects that fell into the subcategory of plays.
After the successes, failures, and cancelations were calculated using the COUNTIFS function, the total number of projects within each funding group was summed to determine what percentage of the campaigns in the funding group were successful. This analysis included all Kickstarter plays globally. 

**Successful campaigns** 
```
=COUNTIFS('Kickstarter campaign'!D:D,"<1000",'Kickstarter campaign'!F:F,"Successful",'Kickstarter campaign'!R:R,"plays")
```

**Failed campaigns**
```
 =COUNTIFS('Kickstarter campaign'!F:F,"failed",'Kickstarter campaign'!D:D,"<1000",'Kickstarter campaign'!R:R,"plays")
```
**Canceled campaigns**
```
=COUNTIFS('Kickstartercampaign'!D:D,"<1000",'Kickstarter campaign'!F:F,"canceled",'Kickstarter campaign'!R:R,"plays")

```
**Total Projects**
```
=SUM(B2:D2)

```


### Challenges and Difficulties Encountered

As with any analysis, there were a few challenges that were encountered.

- The data type in the columns were not formatted correctly. Launch date and end date columns had Unix timestamps. The standard date had to be calculated and formatted for the analysis.

## Results


###### Conclusions made for Outcomes based on Launch date

- The best time to launch a theater campaign is in either May or June. The data suggests that May exceeds expectations of outcomes, while June meets the outcome expected of 100% funding.
- December is the month with the least amount of campaigns. A campaign launched in December had 49% chance of succeeding

###### Conclusions made for Outcomes based on Goal

- Based on goal outcomes, we can clearly see that plays that were launched with goal amount of less than 1000 succeeded (76%). Campaigns with goal amount less than 5000 has a 73% chance of succeeding.
- Campaigns with lesser goal amount succeeded more compared to the campaigns with higher goals. 

###### **Limitations of dataset**

- The dataset has campaign data only up to 2017.
- The list of campaigns totals to only around 4000 for a duration of 9 years all around the world. This data seems pretty less for analysis.

###### **Other possible tables and/or graphs that we could create**

- Charts showing year over year trends for campaign outcomes can be analyzed to see if the demand for a specific category campaign is still high.
- A box-and-whisper plot to identify outliers to improve the analysis.


