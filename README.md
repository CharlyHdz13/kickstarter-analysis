# An Analysis of a Kickstarter Campaign

## Overview of the Project
The play _Fever_ came to a close to its fundraising goal. And now the director wants to analyse different campaigns to compare hers in relation to the other ones, based on dates and their funding goals. 

### Purpose
Using the dataset in this repository I used filters, pivot tables and charts to give the director of _Fever_ a clear breakdown of the other campaings and proposed new alternatives.

## Analysis and Challenges

Two analysis were made to the dataset. One based on the outcomes ( Was the campaign succesful, did it fail or was it canceled?) depending on the launch date of each one. And the other analysis was focused on the outcomes of each campaign based on the monetary goals that they had. 

### Analysis of Outcomes Based on Launch Date

This analysis was made through pivot table, but first some adjustments had to be made to our origninal dataset. Firstly, our focus is only on the campaigns that are related to a play, therefore the column named _Category and Subcategory_ was divided into _Parent Category_ and _Subcategory_. First copying the whole _Category and Subcategory_ column and pasting it into a new column. Afterwards, by using the _Data_ tab of Excel and the function _Text to Columns_ I used the _Delimited_, unchecked the _Tab_ box and checked _Other_ placed a backlash (/) in the box, clicked _next_ and select _Text_ from the _Column data format_ and finished. With these procedure I was able to filter my data based un subcategories and only focus on plays. 

 Before moving on onto the pivot table, there are two new columns that I added: _Date Created Conversion_ and _Years_. The first one is the conversion of the timestamp in UNIX at column J (_Launched_at_) using the following formula: 
 
 `=(((J2/60)/60)/24)+DATE(1970,1,1)`

I just adjusted the format of the cells in to be _date_. To finalize this step in the new column _Years_ I just used the formula `YEAR(S2)` to obtain the year from the column _Date Created Conversion_.

For the pivot table I used the following parameters in the _PivotTable Fields_:

![PivotTableFields](https://user-images.githubusercontent.com/89402038/134092876-8bbe4fb8-76b3-4249-80ee-04a88517451e.png)

As a quick note: when adding the _Date Created Conversion_ parameter to the _rows_ field many other parameters appeared, I just removed them and stayed with the _Date Created Conversion_ parameter. To obtain a table like the following we must filter by _theater_ in the _Parent Category_ filter and by descending order and removing _live_ in the _column label_ filter.

![image](https://user-images.githubusercontent.com/89402038/134093389-1adaeab8-2b65-4d2d-8bbb-99fd1151f89b.png)

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/89402038/134093582-77c3288e-8b6e-4716-aec6-cd23071e36af.png)

As a quick analysis on the data we can percieve that the most successful campaigns were launched during may/june. Nevertheless, also at this time is when there are the most failed campaigns. This is something that we must also look at, although the ratio successful to failed campaigns during this period is the highest. 

### Analysis of Outcomes Based on Goals

For the following analysis I created a whole new sheet with the following table:

![image](https://user-images.githubusercontent.com/89402038/134093909-6d5ad8e5-ea6d-4c49-a65b-0ba8c2b2c8a1.png)

For the first three columns (_Number Successful, Number Failed and Number Canceled_) were made using the formula `COUNTIFS()`. Inside the formula the criteria used were first if the outcome was successful, failed or canceled, then the second criteria was the range were the goal of the campaign was set and finally the last criteria was for the campaign to be a _play_ in the _Subcategory_ column.

The column _Total Projects_ is the sum of the numbers of in the first three columns. Afterwards, to obtain the percentages is just the division of the value on the first three columns dived by the value in _Total Projects_. I just adjusted the format for these values to be in percentage and removed the decimals, in order for them to be round numbers.

Once done all of the above I created the following line chart to view the trends:

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/89402038/134200041-36e4e5e1-af2c-42c3-8807-1ec95eaf2b7c.png)

As a quick analysis on the graph, the best percentage obtained for the succesful campaign is near 80%. This value is obtained when the campaigns have a goal around $1000 to $5000. After this the percentage only decreases and the probability of having a failed campaign just increases. There for the sweet spot for the campaign should be around the values mentioned earlier.

### Challenges and Difficulties Encountered

The most challenges encountered were to know how to filter, organize and use the data, but as explained in the previous two parts these challenges where solved by using formulas from Excel and Pivot tables. A part from those another difficulty perhaps could be to determine which is the best graph that can help us visualize what we want. In this analysis both were line charts because we were interested in identifying trends, but perhaps also a bar graph could have solved our problem. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

  Based on the data, seeing that their is a high number of succesful campaigns launched around May and June shows that around this time is the best to launch a theatrical   campaign. It is also worth noting that around this period of time is when there are the most failed campaigns, regardless of that this period of time is still the best to launcha a campaign because the difference from successful to failed campaigns is the biggest, meaning that a campaign launched during this time will have high probabilities of success.
- What can you conclude about the Outcomes based on Goals?

  As I mentioned earlier the sweet spot to having a successful campaign and setting realistic goals is around $1000 to $5000 this is where the difference between failed and succesful campaigns is the best, therefore increasing the probabilities of having a successful campaign. Increasing the goal will only reduce the probabilities of our play to fail.
- What are some limitations of this dataset?

  As a few limitations I would see that we do not know how many shows each campaign had, the exact location of each and the size of the theater that hosted this campaigns. I think this could be key factors in order to increase the probabilities of having a successful campaign. 

- What are some other possible tables and/or graphs that we could create?
  
  I would also take a look at the ratio between goal and pledged based on launch date, or perhaps take a look into the average donation based of the number of backers that assisted to these campaigns. This perhaps could help us have a better insight onto the best strategy to launch a fundraising campaign.
