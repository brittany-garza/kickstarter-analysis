# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this analysis is to show Louise the outcome of theathers on launching date, along with the the outcome of plays based of goals.   

## Analysis and Challenges

Using the same timestamp code from the module, I was able to convert Unix time to a readable date then used the YEAR formula I extracted the year that each kickstarter featured.

> =(((J2/60)/60)/24)+DATE(1970,1,1)
> =YEAR(S2)

With the code below, I was able to gather outcomes of successful, failed or canceled and change the critera to only show plays. 
The first critera set is to review goal value from the kickstarter sheet (Column D) then only display the total number of goals that are below 1000. 

> =COUNTIFS(Kickstarter!$D:$D, "<1000", Kickstarter!$F:$F, "successful",Kickstarter!$P:$P, "plays")

The following code is filtering all the play goal values that are between 5000 to 9999. 
> =COUNTIFS(Kickstarter!$D:$D, ">=5000", Kickstarter!$F:$F, "successful", Kickstarter!$D:$D,"<=9999", Kickstarter!$P:$P, "plays")


### Analysis of Outcomes Based on Launch Date

May and June were the most successful months for theaters. Decemeber has almost the same amount of successful and failed theaters.
No theaters were canceled in October, but the success rate is only half compared to May and June. 
Only lived theaters were open during the first 3 months of launch.


### Analysis of Outcomes Based on Goals

Plays with the most success had a goal of between 1000 to 4999. All plays either successed or failed. 
Even though 1000 to 4999 has the most susscessful, goals with less than 1000 has a higher percentage. 
No plays were canceled at any time, all either successed or failed. 

### Challenges and Difficulties Encountered

When creating the outcome based on goals chart, I accidently didn't filter by plays instead it counted all categories. If this information was giving to Louise, this would have 
affected her decision on deciding on a goal. I added play to the COUNTIF function and this corrected the data. 

When calculating the average donation, the following code was used from the module content. Without the IFERROR function added to the formula, any average donaton would have an error and excel would not know how to display a value. 

> =IFERROR(ROUND(E2/L2,2),0)


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

  The best months for Louise to premiere her play "Fever" is May and June. If she primeres her play during Decemeber, she will have about 50% chance of failing or successing. 


- What can you conclude about the Outcomes based on Goals?

  She could set her goal amount between 1000 to 4999 since that amount had the highest number of successful plays. If she wants to set a smaller amount, less than 1000 has the   
  highest percentage of success. I think either amount she will have a good chance of having a successful play. 
  

- What are some limitations of this dataset?

  The chart for outcomes for goals is only looking at plays, instead of either musicals or spaces. 
  The chart and graph of theater outcomes only shows for all teathers, instead of breaking it down to show the outcome for the number of plays, musicals or spaces in each year. 


- What are some other possible tables and/or graphs that we could create?

  A box and whisker plot can be used to show Louise a reasonable goal to set for plays based on what the median is. 
  A additional pivot table can be created to show a break down of each year and type of theater had the most or least success. 
