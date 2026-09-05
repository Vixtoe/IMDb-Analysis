# IMDb Top 5000 Movies: Data Analysis & Rating Regression

> Exploratory data analysis and predictive regression modeling on the top 5,000 IMDb movies to identify key rating drivers and forecast user ratings.

---

## Project Overview

This project explores the factors that influence IMDb user ratings across the top 5,000 movies in the Internet Movie Database. By conducting feature engineering, exploratory data analysis, and evaluating multiple linear regression models (OLS, Ridge, and Lasso) through cross-validation, the project predicts overall ratings based on runtime, genres, vote counts, and release years.

---

## Key Questions & Objectives

* **Feature Engineering:** Extract categorical features (such as `main_genre` from multi-genre listings) to improve regression inputs.
* **Exploratory Data Analysis:** Analyze relationships between total vote counts, genres, runtimes, director outputs, and overall ratings.
* **Predictive Modeling:** Train and compare Ordinary Least Squares (OLS) Linear Regression, Ridge Regression, and Lasso Regression across multiple feature sets using cross-validation.

---

## Dataset Overview

The dataset contains 5,000 top movie entries across 12 primary fields:

* **Movie Identification:** `primaryTitle`, `startYear`, `rank`, `tconst`, `Title_IMDb_Link`.
* **Audience Metrics:** `overallRating` (target variable, ranging from 5.9 to 9.3), `numVotes`.
* **Production Metadata:** `runtimeMinutes`, `directors`, `writers`, `genres`.

---

## Exploratory Findings

* **Rating Distribution:** Most movie ratings cluster tightly between 6.7 and 7.6.
* **Votes vs. Rating:** A positive correlation exists between total votes and overall ratings, indicating strong audience consensus for popular titles.
* **Runtime Impact:** Movies exceeding 120 minutes show higher median ratings compared to shorter runtime categories (<90 mins and 90–120 mins).
* **Genre Breakdown:** Action is the most frequent main genre, while less frequent genres (e.g., Western) exhibit higher overall average ratings.
* **Director Frequency:** Woody Allen leads in overall movie count within the dataset, followed by Clint Eastwood and Steven Spielberg.

---

## Machine Learning Results & Model Comparison

Models were evaluated using Mean Cross-Validation Mean Squared Error (CV MSE) across `base`, `movie`, and `full` feature sets:

* **Best Performing Model:** Ridge Regression ($\alpha = 0.1$) on the full feature set.
* **Test Performance:** Test MSE of **0.21** (RMSE $\approx$ **0.46 rating points**).
* **Summary Benchmark:** Ridge Regression outperformed standard Linear Regression and Lasso Regularization, providing reliable rating predictions within a $\approx 0.46$ margin.

---

## Documentation & Code Artifacts

* **Source Code / Notebook:** Available in [`notebooks/imdb_data_analysis.ipynb`](notebooks/imdb_data_analysis.ipynb) or [`src/imdb_regression.py`](src/imdb_regression.py).
* **Presentation Deck:** [View Presentation Slides (PDF)](docs/presentation.pdf)
* **Dataset:** [`data/imdb_top_5000.csv`](data/imdb_top_5000.csv)

---

## Tech Stack & Tools

* **Language:** Python
* **Data Processing & ML:** Pandas, NumPy, Scikit-Learn (Linear Regression, Ridge, Lasso)
* **Visualization:** Matplotlib, Seaborn
* **Academic Context:** Developed for CN240 Introduction to Data Science at Thammasat School of Engineering

---

## Team & Individual Contributions

* **Academic Course:** CN240 Introduction to Data Science
* **Author:** Chanoudom Tann (Victor)
* **Individual Contributions:**
  * Cleaned and parsed the IMDb dataset, performing feature extraction on multi-genre strings.
  * Conducted EDA visualizations for runtime, vote distributions, and director frequencies.
  * Built, tuned, and evaluated Linear, Ridge, and Lasso regression algorithms using cross-validation.

---

## Project Structure

```text
imdb-rating-regression/
├── data/
│   └── imdb_top_5000.csv
├── docs/
│   └── presentation.pdf
├── notebooks/
│   └── imdb_data_analysis.ipynb
├── src/
│   └── imdb_regression.py
├── requirements.txt
└── README.md
