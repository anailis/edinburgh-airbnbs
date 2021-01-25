# Edinburgh Airbnbs

## Introduction

**This is a work in progress.**

The aim of this project is to use InsideAirbnb's datasets on Edinburgh Airbnbs 2019 - 2021 to answer a range of questions. At the end of the project, recommendations will be made about how it could be followed up.

The questions at the outset of this project are:
- Are Airbnbs priced differently depending on what area they are in?
- Has the number of Airbnbs in Edinburgh, their price, or availability changed post-Covid compared to pre-Covid?
- How well can Edinburgh Airbnb prices be predicted from InsideAirbnb's data alone?

## Results

**Are Airbnbs priced differently depending on what area they are in?**

This is a simple, descriptive question that can be addressed by simply examining the means and spreads of Airbnb pricing in a certain area. Here, price is the mean price over the period June 2019 to June 2020 per included guest and excluding additional fees such as cleaning fees. The boxplot makes evident that there are a number of luxury properties in most areas, but the vast majority are below £200 a night per included guest.

![](../master/eda/neighbourhood_pricepig_boxplot.png)

The three cheapest areas to stay are Leith, Haymarket, and Bruntsfield. This is also true of the 2020-21 data. New Town is the most expensive location for Airbnbs in both this and the following years' data. I also made interactive choropleth's for viewing pricing of Edinburgh Airbnbs - the interactive version can be found in `eda/mapvis.ipynb`. 

![](../master/eda/price_choropleth.PNG)

**Has the number of Airbnbs in Edinburgh, their price, or availability changed post-Covid compared to pre-Covid?**

The Airbnb data show clear seasonality with spikes in price around August and the end of December. These spikes coincide with some of Edinburgh's biggest events: the Edinburgh Fringe Festival in August and the Christmas Markets and Hogmanay street party at the end of December. 

![](../master/eda/monthly_seasonality.png)

There are also weekly fluctuations: Friday and Saturday nights are more expensive than other days of the week.

![](../master/eda/weekly_seasonality.png)

When the data for the 2020-21 period were collected, in July of 2020, Airbnb owners would have been well aware of the COVID-19 pandemic and its impact on travel and events. In fact, the Edinburgh Fringe Festival was cancelled on the 1st April 2020, before these data were collected. So did Edinburgh Airbnb owners drop their prices to reflect the decrease in demand for their properties during this time?

[graph to come]

Visually, it seems clear that prices were not amended...

Perhaps Airbnb owners took their properties off of the holiday letting site and made them into regular rentals...


**How well can Edinburgh Airbnb prices be predicted from InsideAirbnb's data alone?**

## Conclusions & Recommendations 
