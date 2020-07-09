---
layout: post
title: "Using ggmap and gganimate to model Central Park Squirrel Activity"
comments: true
description: "Learn how to use ggmap and gganimate using data from the 2018 Central Park Squirrel Census"
keywords: "ggmap, gganimate, squirrel census, request"
categories: blog
---

```
library(ggmap)
library(gganimate)
library(dplyr)
library(reshape2)

data <- X2018_Central_Park_Squirrel_Census_Squirrel_Data %>% select("Date", "X", "Y", "Running", "Chasing", "Climbing", "Eating", "Foraging")

data$activity <- ifelse(data$Running == TRUE, "Running", ifelse(data$Chasing == TRUE, "Chasing", ifelse(data$Climbing == TRUE, "Climbing", ifelse(data$Eating == TRUE, "Eating", ifelse(data$Foraging == TRUE, "Foraging", NA)))))

map <- qmplot(X, Y, data = data, colour = activity, main = "Central Park Squirrel Activity")

map + labs(subtitle ="Data from City of New York City 2018 Squirrel Census
Date: {frame_time}", caption = "Created by Joanna @datatutorials") + transition_time(Date)
```

<img src="/assets/images/dt_squirrels.gif" alt="Squirrel graph">
