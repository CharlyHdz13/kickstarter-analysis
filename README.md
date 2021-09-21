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

For the first three columns (_Number Successful, Number Failed, Number Canceled_)
![ParentCategoryOutcomesUS](https://user-images.githubusercontent.com/89402038/133488104-0836470c-c705-4a13-91dc-66220299a133.png)
![OutcomesBasedOnLaunchDate](https://user-images.githubusercontent.com/89402038/133488096-d4d2cd52-4cdc-4e0a-825b-3a3da245a2fe.png)

As shown in the previous two images an analysis was made first on a macro perspective to determine the best campaign to raise funds for our project and afterwards based on the date provided establish the best time of the year to execute the campaign.
## Recomendations
I should suggest focusing on theatre for our crowdfunding and focus on launching this campaign during May-June, because normally this correlates to succesful campaigns.
