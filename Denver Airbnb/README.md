# Airbnb Pricing Patterns in Denver

## Overview

This project analyzes Airbnb prices in Denver using public listing data from InsideAirbnb. The goal was to understand whether some areas are expensive because of their location or because they contain larger properties on average.

The main question was:

**Is the southeast area of Denver more expensive because of location, or because listings there are larger on average?**

## Project Goal

To answer this question, I built two Generalized Additive Models (GAMs):

1. A location-only model using latitude and longitude.
2. A full model that also includes listing features such as bedrooms, number of guests, room type, and review scores.

Comparing these models allowed me to separate the effect of location from the effect of property characteristics.

## Dataset

The data comes from the public InsideAirbnb dataset for Denver.

Key variables included:

- Price per night
- Latitude and longitude
- Number of bedrooms
- Number of guests accommodated
- Room type
- Review score
- Neighborhood

## Methods

- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Geographic visualization using maps
- Generalized Additive Models (GAMs)
- Spatial contour mapping
- Model comparison

## Key Findings

The location-only model suggested that southeast Denver was the most expensive area.

However, after controlling for listing characteristics such as bedrooms, accommodations, room type, and review scores, Downtown Denver became the most expensive location.

This indicates that the southeast appears expensive mainly because it contains larger properties, while Downtown Denver has the strongest location premium.

## Results

| Model | R² |
|---------|---------|
| Location-Only GAM | ~0.08 |
| Full GAM | ~0.58 |

The full model explained substantially more variation in Airbnb prices.

## Visualizations

The project includes:

- Distribution of Airbnb listings across Denver
- Top 8 most expensive neighborhoods
- Geographic map of expensive neighborhoods
- Location-only GAM prediction map
- Full GAM prediction map
- Difference map comparing both models

## Tools Used

- R
- tidyverse
- ggplot2
- mgcv
- dplyr
- viridis
- maps
- broom
- ggrepel
- knitr

## Conclusion

Simple average prices can be misleading. While southeast Denver appears to have the highest Airbnb prices, much of this difference is explained by larger listings. After controlling for listing characteristics, Downtown Denver shows the strongest location value.

This project demonstrates how statistical modeling can separate location effects from property characteristics and provide more accurate insights into housing markets.

## Files

- `Final_EDA_Project.Rmd` - Main analysis
- `Final_EDA_Project.pdf` - Final report
- `listings.csv` - Dataset from InsideAirbnb
