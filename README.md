---
title: 'Course Project: Shiny Application and Reproducible Pitch'
author: "Mohammed Hosayn"
date: "22.08. 2021"
output: ioslides_presentation
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = FALSE)
```

## About the Course Project

This is a deliverable for the course Developing Data Products as part of the Coursera Data Science Specialization.

Instructions:

1. Write a shiny application with associated supporting documentation. The documentation should be thought of as whatever a user will need to get started using your application.
2. Deploy the application on Rstudio's shiny server
3. Share the application link by pasting it into the provided text box
4. Share your server.R and ui.R code on github

## How to use the application

Using the data provided by Galton Families dataset, we fit a linear model to predict a child's height based on the gender and parent's average height.

The application is running on (https://hosayn.shinyapps.io/1234/?_ga=2.258813646.55856615.1629639865-814300781.1629639865)

ui.R, and Server.R Code in my github repository ()

## Galton Families Dataset

The data used in the app comes from the GaltonFamilies dataset. 

```{r summary}
library(HistData)
data(GaltonFamilies)
summary(GaltonFamilies)
```

## Plot
In the scatterplot below are represented the data used for the prediction model
```{r plot}
library(HistData)
data(GaltonFamilies)
plot(jitter(GaltonFamilies$childHeight) ~ GaltonFamilies$midparentHeight,xlab="Average Height of the Parents (in inches)",ylab="Height of the Child (in inches)",main="Scatterplot of Galton Family Data",pch=19,frame.plot=FALSE,col=ifelse(GaltonFamilies$gender=="female", "pink", "light blue"))
legend(65,80,pch=c(19,19),col=c("pink","light blue"),c("female", "male"),bty="o",cex=.8)
```
