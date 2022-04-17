# **Kickstarting with Excel**

## Overview of Project
Performing analysis on Kickstarter data to uncover trends

### Purpose
This analysis explores how past Kickstarter campaigns performed in relation to their launch dates and funding goals in order to povide insight for future campaign planning. It focuses primarily on campaigns for plays and/or within the theater category. 

## Analysis and Challenges

### **Outcomes Based on Launch Date**

A pivot table was created from the dataset to explore the relationship bewtween outcomes and the month launched, live campaigns were excluded. The table was then filtered to show only Theater campaigns.

![Theater_Outcomes_vs_Launch_Table](https://user-images.githubusercontent.com/99051640/162850411-9fbfbdab-cd6a-4721-9d4c-9ff6b41fcfd9.png)

Next, a marked line chart was created from the table to visualize this relationship and was evaluated for trends of individual outcomes over time as well as the ratio of outcomes.

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/99051640/162845302-b4b2a1f4-a88f-4f98-8e4b-725e84dc0228.png)

#### Challenges
When exploring the chart and table it became apparent that specific years had significantly less available data for theater launches than others. To overcome this challenge in the analysys additional charts and tables were created to visualize the impact on my origial conclusions. This is explained in [Further Exploration](https://github.com/TheodoraNell/Kickstarter-analysis#further-exploration)


### **Outcomes Based on Goals**

A new sheet was added with a table comapring outcomes and different funding goal ranges. The table included both number and percentage of outcomes. In order to populate the fields for number of outcomes `COUNTIFS` was used:

> `COUNTIFS(Kickstarter!D2:D4115, "<1000", Kickstarter!R2:R4115, "plays", Kickstarter!F2:F4115, "successful")`

Percentage of Outcomes and Total Projects were also calculated:

> `B2/E2`
> `SUM(B2:D2)`

![Outcomes_Based_on_Goals_Table](https://user-images.githubusercontent.com/99051640/162846325-d9ab63db-0148-4251-8df5-6a392627e70e.png)

A line chart was then created form the table to evaluate the outcomes of different goal ranges. The visualization of higher goal ranges differed from what was expected which prompted a closer look, which is detailed in [Further Exploration](https://github.com/TheodoraNell/Kickstarter-analysis#further-exploration)

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/99051640/162846363-205f7e5e-084a-4f01-b04a-3b25601d4712.png)

#### Challenges
While exploring the chart and table and referencing the original dataset it became apparent that the values for funding goals were not all in the same currency. Creating another column for currencies converted to USD was considered however in doing so, the values would still inaccurate given that exchange rates commonly fluxuate and at times significantly so. Another option would be to edit the 'COUNTIFS' function to filter the Currency column and isolate data for one currency at a time. 

 
## Results

### **Outcomes Based on Launch Date**

It can be concluded that May fared the best in terms of successful vs failed outcomes. It can also be concluded that December was the least successful month. These two months were also the most and least popular months to launch a campaign respectively. 

### **Outcomes Based on Goals**

It can be concluded that campaings with funding goals under $5000 had the highest occurrence of successful outcomes. 

### **Limitations of the Data**

#### The data is incomplete
In addition to not being very current, the range of the theater data does not include the first half of 2010 and most of 2017. Additionally only two years had theater campaigns launched every month so comprehensive comparison of months is only possible for a small sample.

#### Inconsistent units across datapoints
The values under Funding Goals are shown in different currencies so when comparing them the data is misrepresented. Because there is another column denoting the currency type it would be possible to convert them all to the same currency. However, with exhange rates fluxuating and sometimes varying widely over years the data would still be innacurate unelss the exchange rates were calculated for each specific launch date.

### **Further Exploration**

By visualizing the data in bar chart form and with percentages, it can be concluded that October also did not fair well in terms of outcomes despite being a more popular month to launch.
![Theater_Outcomes_vs_Launch_Percentage](https://user-images.githubusercontent.com/99051640/162847250-3ed94b73-773d-4ba2-ba57-c40114373072.png)
![Theater_Outcomes_vs_Launch_Bar](https://user-images.githubusercontent.com/99051640/162847283-506057b5-dd9c-4983-aeae-86f8d61dfd69.png)

![Theater_Outcomes_vs_Month_Year](https://user-images.githubusercontent.com/99051640/162847567-8ed6c5fb-3ca5-418c-9664-f87750044c34.png)
![Data_Distribution_Months_vs_Years_Table](https://user-images.githubusercontent.com/99051640/162848083-e3cb4248-2376-4c98-886a-49c7895ead4f.png)
By visualizing Outcomes based on years it is possible to evaluate how entire years fared. It is also made clear that the number of datapoints varies year to year, which can be seen even more clearly in the subsequent table.

Because 2015 and 2016 are the only years with data for every month, visualizing them separately allows for comparison to the original *Theater Outcomes vs Launch* chart [in this section](https://github.com/TheodoraNell/Kickstarter-analysis#outcomes-based-on-launch-date)
![2015_2016_Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/99051640/162850804-53d13057-ff70-4324-9131-24af2508f566.png)
![2015_Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/99051640/162851069-9320fda0-f38b-4b7c-967e-18d949e6d17b.png)
![2016_Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/99051640/162851073-9108e966-cfc3-4c2f-9011-d5b2012bc56f.png)

A Revised *Outcomes vs Funding Goal* chart with converted currency values could be created. As previously mentioned [here](https://github.com/TheodoraNell/Kickstarter-analysis#inconsistent-units-across-datapoints), another column could be added to the datasheet with goals converted to USD with current exchange rates in order to recreate the original *Outcomes vs Funding Goal* line graph in [this section](https://github.com/TheodoraNell/Kickstarter-analysis#outcomes-based-on-goals) The values would still be innacurate but the revised chart would partially correct for currencies that typically vary widely from USD. 

Finally, a table showing the relationship between average donations, average number of backers, and outcomes. The goal was to provide insight into the success of some of the higher goal ranges. It also raises the question of there being different types of backer groups represented: large backer groups making relatively small donations and smaller groups making larger donations. ("Count of Goal" represents how many campaings had that specific goal)
![Funding_Goals_vs_Backers_Table](https://user-images.githubusercontent.com/99051640/162849283-e1ae3577-8e26-4d12-be67-c5a03d5731c9.png)


