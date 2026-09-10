# pga-tour-performance-analytics

PGA Tour Performance Analytics Project

A solo data analysis project exploring which aspects of professional golf performance measured through PGA Tour "Strokes Gained" statistics most strongly predict a player's tournament finishing position.

## Overview

Using a large-scale PGA Tour dataset, this project cleans and analyzes Strokes Gained metrics and builds a multiple linear regression model to predict player finishing position. The model was applied to the 2023 PGA Championship and correctly placed 2 of the actual top-10 finishers.

## What Are Strokes Gained?

Strokes Gained is the PGA Tour's standard metric for measuring player performance relative to the field, broken into components:

* SG: Putting — performance on the greens
* SG: Approach — performance on approach shots
* SG: Around-the-Green — performance on short game shots near the green
* SG: Off-the-Tee — performance on tee shots
* SG: Tee-to-Green — combined ball-striking performance (excludes putting)

## Process
1. Data Cleaning — Removed rows with missing Strokes Gained values to ensure a complete dataset for modeling.
2. Exploratory Analysis — Used ggplot2 to visualize relationships in the data, including the correlation between hole par and strokes taken.
3. Modeling — Built a multiple linear regression model (lm()) using pos ~ sg_putt + sg_arg + sg_ott + sg_app + sg_t2g to predict finishing position from Strokes Gained components.
4. Application — Applied the trained model to 2023 PGA Championship data, correctly identifying 2 of the actual top-10 finishers.

## Tools & Libraries
* R
* tidyverse
* dplyr
* ggplot2

## Files
* projectPGA.Rmd — Full analysis: data cleaning, exploratory visualizations, and regression model.

## Key Takeaway

Strokes Gained components, particularly tee-to-green performance, carry meaningful predictive signal for tournament outcomes, even with a relatively simple linear model.

## Future Improvements
Address multicollinearity between sg_total and its individual components (e.g., by dropping sg_total from the predictor set, since it is a linear combination of the others).
Validate the model on additional tournaments to test generalizability.
Experiment with non-linear models (e.g., random forest) to capture more complex relationships between Strokes Gained components and finishing position.
