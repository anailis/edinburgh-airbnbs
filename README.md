# Edinburgh Airbnbs

## Introduction

The aim of this project is to use InsideAirbnb's datasets on Edinburgh Airbnbs 2019 - 2021 to answer a range of questions. At the end of the project, recommendations will be made about how it could be followed up.

The questions at the outset of this project are:
- Are Airbnbs priced differently depending on what area they are in?
- Has the number of Airbnbs in Edinburgh or their price changed post-Covid compared to pre-Covid?
- How well can Edinburgh Airbnb prices be predicted from InsideAirbnb's data alone?

## Results

**Are Airbnbs priced differently depending on what area they are in?**

This is a simple, descriptive question that can be addressed by simply examining the means and spreads of Airbnb pricing in a certain area. Here, price is the mean price over the period June 2019 to June 2020 per included guest and excluding additional fees such as cleaning fees. The boxplot makes evident that there are a number of luxury properties in most areas, but the vast majority are below £200 a night per included guest.

![](../master/eda/neighbourhood_pricepig_boxplot.png)

The three cheapest areas to stay are Leith, Haymarket, and Bruntsfield. This is also true of the 2020-21 data. New Town is the most expensive location for Airbnbs in both this and the following years' data. I also made interactive choropleth's for viewing pricing of Edinburgh Airbnbs - the interactive version can be found in `eda/mapvis.ipynb`. 

![](../master/eda/price_choropleth.PNG)

**Has the number of Airbnbs in Edinburgh or their price changed post-Covid compared to pre-Covid?**

The Airbnb data show clear seasonality with spikes in price around August and the end of December. These spikes coincide with some of Edinburgh's biggest events: the Edinburgh Fringe Festival in August and the Christmas Markets and Hogmanay street party at the end of December. 

![](../master/eda/monthly_seasonality.png)

There are also weekly fluctuations: Friday and Saturday nights are more expensive than other days of the week.

![](../master/eda/weekly_seasonality.png)

When the data for the 2020-21 period were collected, in July of 2020, Airbnb owners would have been well aware of the COVID-19 pandemic and its impact on travel and events. In fact, the Edinburgh Fringe Festival was cancelled on the 1st April 2020, before these data were collected. So did Edinburgh Airbnb owners drop their prices to reflect the decrease in demand for their properties during this time?

![](../master/eda/year_price_comparison.png)

There is still a spike in Airbnb pricing during the period when the Fringe festival would have been. However, the magnitude of this spike is less than the previous year. The data available through InsideAirbnb cannot be used to investigate changes in bookings, because Airbnb does not differentiate between a let that has been booked and a let that has been set as unavailable by the property owner. Some owners, for example, will only let their property out during a specific time of year. 

Perhaps Airbnb owners took their properties off of the holiday letting site and made them into regular rentals? The number of Airbnb's in the 2019-20 dataset was 13,245 and in the 2020-21 it was modestly less: 12,658. Of the Airbnbs listed in the 2019-20 dataset, 8,126 (~61%) of their IDs were also found in the 2020-21 dataset. There could conceivably be even more relisted under different IDs. However, without other years for context there is little that we can learn from these numbers. 

**How well can Edinburgh Airbnb prices be predicted from InsideAirbnb's data alone?**

Principal components analysis (PCA) was used to reduce the dimensionality of review data, and multiple correspondance analysis (MCA) was used to reduce the dimensionality of amenity variables. Data were modelled with a multivariate regression and XGBoost in an attempt to predict prices from the other available data. The regression performed marginally better on test data (r^2 = 0.15) compared to XGBoost (r^2 = 0.12). Overall though, there is not a great amount of predictive power contained only within the InsideAirbnb dataset. 

## Conclusions & Recommendations 

To better model Airbnb pricing in Edinburgh, I would recommend the incorporation of additional datasets. The InsideAirbnb data gives co-ordinates of Airbnb locations which will allow integration with spatial datasets. These could include, but are not limited to:
- Number and proximity of surrounding amentities (bars, restaurants, etc.) 
- Distance from key landmarks (Royal Mile, Grassmarket etc.)
- Average rent of surrounding properties with a certain radius 

There is also scope to create time series models given the seasonality of Edinburgh Airbnb pricing. 

To further investigate differences in Airbnb pricing from area to area, prices of Airbnbs could have been corrected for other features other than just the number of guests. However, few other features should strong correlations (> |0.1|) with price so it was unclear how to make properties comparable. I was somewhat surprised about how minor the differences were between centrally located neighbourhoods and those further afield. Perhaps text analysis of property descriptions and reviews could reveal more details about properties. Additionally, the aforementioned integration with spatial datasets may also provide more insights. General neighbourhood may be less important than proximity to a particular landmark, such as Edinburgh Castle.

Finally, the spike in Airbnb pricing at peak tourist times in 2020, despite owners knowing about the cancellation of festivals, is an interesting finding. This could be down to inertia on the owner's part, or reliance on Airbnb's Smart Pricing feature, which automatically sets property prices based on expected demand. 
