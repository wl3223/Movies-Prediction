# TMDB Movie Revenue and Ratings Prediction

**Authors**: Weiyi Lu & Liuyang Bai

This repository contains the analysis, code, and findings for predicting movie box-office success and audience reception using strictly pre-release metadata. 

By analyzing 3,532 movies released between 2010 and 2024 from The Movie Database (TMDB), this project explores how well structured, early-stage attributes can forecast a film's commercial and critical outcomes.

## Repository Structure

* `paper.pdf`: Full project research paper containing detailed methodology, evaluation metrics, and error analysis.
* `EDA.ipynb`: Source code for API data collection, data cleaning and EDA analysis.
* `modeling.ipynb`: Feature engineering and modeling.

## Project Overview

To ensure the resulting models offer practical value for studio planning and marketing decisions, we restrict our feature set entirely to information known prior to a movie's release, including production budget, runtime, genres, release timing, and talent track records. 

Models were evaluated across two primary tasks using a strict time-based split: training on pre-2021 releases, validating on 2022 releases, and testing on 2023–2024 releases.

### 1. Revenue Prediction (Regression)
* **Objective:** Predict the log-transformed box-office revenue.
* **Best Model:** Ridge Regression.
* **Key Takeaway:** Commercial success is substantially more predictable than critical success. A film's production budget is by far the strongest pre-release signal of its eventual box-office return.

### 2. High-Rating Prediction (Classification)
* **Objective:** Predict whether a film will achieve strong audience reception, defined as a TMDB vote average of at least 7.0.
* **Best Model:** Gradient Boosting Machine with validation-tuned decision thresholding.
* **Key Takeaway:** Perceived quality is much harder to forecast from structured metadata alone. Critical success relies on a nuanced mix of runtime, keywords, genre, and director experience, while massive budgets surprisingly show a negative correlation with high audience ratings.
