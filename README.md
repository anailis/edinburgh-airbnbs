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

This is a simple, descriptive question that can be addressed by simply examining the medians and standard deviations of Airbnb pricing in a certain area. Here, price is the mean price over the period June 2019 to June 2020 per included guest and excluding additional fees such as cleaning fees. Medians are preferred over means in this context as the pricing data is heavily right skewed due to a number of luxury properties. 

![](../master/eda/neighbourhood_pricepig_boxplot.png)

The three cheapest areas to stay are Leith, Haymarket, and Bruntsfield. This is also true of the 2020-21 data. New Town is the most expensive location for Airbnbs in both this and the following years' data. The difference between the median prices in Haymarket compared to New Town is £20.

To come: geographical plot...

**Has the number of Airbnbs in Edinburgh, their price, or availability changed post-Covid compared to pre-Covid?**

## Conclusions & Recommendations 
