---
title: Time Series in R | Examples | Plotly
name: Time Series
permalink: r/time-series/
description: How to plot date and time in R. An example of a time series plot with the POSIXct and Sys.Date classes.
layout: base
thumbnail: thumbnail/time-series.jpg
language: r
page_type: example_index
has_thumbnail: true
display_as: chart_type
order: 10
output:
  html_document:
    keep_md: true
---



### New to Plotly?

Plotly's R library is free and open source! [Get started](https://plot.ly/r/getting-started/) by downloading the client and [reading the primer](https://plot.ly/r/getting-started/). 
You can set up Plotly to work in [online](https://plot.ly/r/getting-started/#hosting-graphs-in-your-online-plotly-account) or [offline](https://plot.ly/r/offline/) mode. 
We also have a quick-reference [cheatsheet](https://images.plot.ly/plotly-documentation/images/r_cheat_sheet.pdf) (new!) to help you get started!

### Dates


```r
library(plotly)
today <- Sys.Date()
tm <- seq(0, 600, by = 10)
x <- today - tm
y <- rnorm(length(x))
plot_ly(x = ~x, y = ~y, text = paste(tm, "days from today"))
```

<iframe src="https://plot.ly/~RPlotBot/3467.embed" width="800" height="600" id="igraph" scrolling="no" seamless="seamless" frameBorder="0"> </iframe>

### POSIXlt date time class with timezone


```r
library(plotly)
now_lt <- as.POSIXlt(Sys.time(), tz = "GMT")
tm <- seq(0, 600, by = 10)
x <- now_lt - tm
y <- rnorm(length(x))
plot_ly(x = ~x, y = ~y, text = paste(tm, "seconds from now in GMT"))
```

<iframe src="https://plot.ly/~RPlotBot/3461.embed" width="800" height="600" id="igraph" scrolling="no" seamless="seamless" frameBorder="0"> </iframe>

### POSIXct date time class without timezone


```r
library(plotly)
now_ct <- as.POSIXct(Sys.time())
tm <- seq(0, 600, by = 10)
x <- now_ct - tm
y <- rnorm(length(x))
plot_ly(x = ~x, y = ~y, text = paste(tm, "seconds from now in", Sys.timezone()))
```

<iframe src="https://plot.ly/~RPlotBot/3463.embed" width="800" height="600" id="igraph" scrolling="no" seamless="seamless" frameBorder="0"> </iframe>