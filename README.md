# An Analysis of a Kickstarter Campaign

## Overview of the Project
The play _Fever_ came to a close to its fundraising goal. And now the director wants to analyse different campaigns to compare hers in relation to the other ones, based on dates and their funding goals. 

### Purpose
Using the dataset in this repository I used filters, pivot tables and charts to give the director of _Fever_ a clear breakdown of the other campaings and proposed new alternatives.

## Analysis and Challenges

Two analysis were made to the dataset. One based on the outcomes ( Was the campaign succesful, did it fail or was it canceled?) depending on the launch date of each one. And the other analysis was focused on the outcomes of each campaign based on the monetary goals that they had. 

### Analysis of Outcomes Based on Launch Date

This analysis was made through pivot tables, but first some adjustments had to be made to our origninal dataset. Firstly, our focus is only on the campaigns that are related to a play, therefore the column named _Category and Subcategory_ was divided into _Parent Category_ and _Subcategory_. First copying the whole _Category and Subcategory_ column and pasting it into a new column. Afterwards, by using the _Data_ tab of Excel and the function _Text to Columns_ I used the _Delimited_, unchecked the _Tab_ box and checked _Other_ placed a backlash (/) in the box, clicked _next_ and select _Text_ from the _Column data format_ and finished. With these procedure I was able to filter my data based un subcategories and only focus on plays. 

![ParentCategoryOutcomesUS](https://user-images.githubusercontent.com/89402038/133488104-0836470c-c705-4a13-91dc-66220299a133.png)
![OutcomesBasedOnLaunchDate](https://user-images.githubusercontent.com/89402038/133488096-d4d2cd52-4cdc-4e0a-825b-3a3da245a2fe.png)

As shown in the previous two images an analysis was made first on a macro perspective to determine the best campaign to raise funds for our project and afterwards based on the date provided establish the best time of the year to execute the campaign.
## Recomendations
I should suggest focusing on theatre for our crowdfunding and focus on launching this campaign during May-June, because normally this correlates to succesful campaigns.
