# Kickstarting with Excel
Performing analysis on kickstarter data to uncover trends.
## Overview of Project
The kickstarter campaigns data set was analysed to help Louise understand how different campaigns performed in meeting their targets. How the goal amount affected the success of a campaign and how timing of the campaign also had a say in its status. Throughout the module, the given information was used to show both analytically and visually how campaigns in different categories and subcategories have been performing. The conclusion was that out of all campaigns the category Theater performed the best and the subcategory Plays was the most successful. 

![image](https://user-images.githubusercontent.com/87828174/131266123-5e45350c-7794-4292-bbf4-40a9a08d6814.png) 

![image](https://user-images.githubusercontent.com/87828174/131266910-bfcff984-2cb3-4c9f-9e90-439ff0e3db9f.png)

### Purpose
The purpose of the assignment analysis was for Louise to understand how different campaigns in the category Theater and subcategory Plays performed in relation to their goal amounts, timing and type of campaign.
## Analysis and Challenges
### Analysis of Outcomes based on Launch Date
In this section, an analysis was done of the Theater campaigns and their performance in regards to the launch date of the campaign. An additional column was added to the data set and using the **year()** function, the years were calculated from the launch dates which had previously been converted from Unix timestamps. A pivot table was made with outcomes and months. This was filtered by year and parent categories to see specifically the monthly performance of Theater campaigns. Using the pivot table, a chart was made to show the relationship between months and outcome visually and to find a trend. 

![image](https://user-images.githubusercontent.com/87828174/131266512-105fb459-023a-4dfb-aa6e-f68a73c1433b.png) 

### Analysis of Outcomes based on Goals
In this part, we had to show how the subcategory plays which Louise is interested in, performed in relation to goal amounts. Goal being the amount set to be achieved by the campaign. Disregarding the current live or ongoing campaigns, we had to calculate the number of successful, canceled and failed campaigns for specific ranges of goal amounts as shown below. 

<img width="1035" alt="Screenshot 2021-08-29 at 18 14 25" src="https://user-images.githubusercontent.com/87828174/131266977-41926ed3-462c-4cc6-bafe-4a617a117785.png"> 

These goal dollar-amounts ranged from below 1,000 to above 50,000. A way to count the number of successful, failed and canceled campaigns was to filter the data set to show only Plays and filter the Goal amount to fit the range for which we wanted to calculate the outcomes. A simpler and more time efficient way was found to calculate the outcomes of these goal ranges by using the **COUNTIF** function. For example, for the second row range of 1000 to 4999, the following code was used:
  
**=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999",Kickstarter!$R:$R, "plays",Kickstarter!$F:$F, "successful")**
  
The function basically instructs to use the data from the 'Kickstarter' sheet and sets a range for values allowed in column D which is the goals column. This range as stated is 1000=<x<=4999. Secondly the value in column R or the subcategory column must be 'plays' while the outcome column or column F must be 'successful'. This limits the data set and counts only those instances where all these requirements are fullfilled. 
* Goal Amount is greater than and equal to 1000 while being less than and equal to 4999.
* Subcategory = 'plays'
* Outcome = 'successful'
  
<BR> Similarly the range values and outcomes were changed in the formula to individually count and record all instances of a certain outcome for a certain range as shown above. After calculating the number of each outcome for each range, the total amount of projects including all outcomes was calculated for each range using the **Sum** formula. Lastly the percentage of successful, failed and canceled outcomes was calculated for each range using the outcome counts and total number of projects for that range. A chart was created to visually represent the relationship between the percentage for each outcome versus the goal range for that outcome as shown below.
  
![image](https://user-images.githubusercontent.com/87828174/131267852-03ead31d-682a-4466-b8ed-0b88543ec554.png)
  
### Challenges and Difficulties encountered
  Possible challenges that could be faced calculating the number of outcomes for each goal range. This is easily solved using the **COUNTIF** function.
  
## Results
### Results of Outcomes based on Launch date
  Looking at the line graph made, one can see the trend, for Theater, the best launch month was May. The number of successful campaigns for Theater was highest for those launched in May while it was lowest for those launched in December. Similarly the highest number of failed campaigns started in May and the lowest in November. This is also due to the fact the highest number of campaign start dates are in May while the lowest number of campaign starts are in December.
  
### Results of Outcomes based on Goals
  For the subcategory Plays, there were 694 successful projects, 353 failed campaigns and 0 cancelled. Looking at the line graph, one can see the trend of the percentage of successful projects being higher for lower goal amounts. That is when the amount needed or the goal amount was less than 1000, the percentage of successful campaign was maximum. As the goal amount increased, the percentage of failed campaigns increased in relation to successful ones. Until the range of 15,000 to 19,999, the successful campaigns outnumber the failed campaigns and we can say from 0 to 20,000 goal amount, the percentage of successful campaigns is more than the failed ones. Therefore a budget of 0 to 19,999 has a higher chance of succeeding in fullfiling its goal amount than for rnages higher than this. There is a spike of successful campaigns outweighing the failed campaigns in the range of 35000 to 40000 but these could be due to other factors such as the content of these plays; if they were attractive to people or due to location of these kickstarters. Folowing the general trend, in the largest goal amounts, the percentage of successful campaigns goes to 0 or near 0 as most kickstarter campaigns with extremely high goals failed due to majorly lack of funding. 

### Limitations of the data set and improvements which can be made
  Looking at the graphs, one can see basic trends of success of campaigns in relation to start dates and in relation to goal amounts. Location of kickstarters and a graph of how different countries performed in comparison to others would help in understanding the relation between outcomes and location. There are other factors involved in the outcome of a campaign such as content of a campaign and how attractive it is to the public. A graph of number of backers for each successful campaign in different categories would help us understand the popularity of certain campaigns and how that helps in achieving a set goal. Lastly for plays specifically, a graph of outcomes vs genre of the play would help Louise and us understand if certain types of content perform better in these kickstarters and whether certain genres are more popular for the public. The data set would be more accurate if thee goal and pledged column data was normalised to a single currency.

 
