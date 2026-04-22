# Netflix Movies & TV Shows Data Analysis

## Project Overview
This project is part of the **Foundations of Data Science** course (Capstone Project 1). The objective is to perform a comprehensive data analysis on a dataset of Netflix movies and TV shows to uncover trends in genres, ratings, and popularity.

## Problem Statement
The entertainment industry is highly competitive, and content streaming platforms like Netflix need to understand viewer preferences and content performance to make informed decisions. This project aims to analyze movie data to identify:
- Which genres are most prevalent.
- The distribution of ratings among the content.
- Trends in movie ratings over the years.
- The relationship between content duration and viewer ratings.

## Dataset Description
- **File**: `n_movies.csv`
- **Rows**: ~10,000 (before cleaning)
- **Features**:
  - `title`: Name of the movie or TV show.
  - `year`: Release year.
  - `certificate`: Content rating (e.g., TV-MA, PG-13).
  - `duration`: Length of the content (in minutes).
  - `genre`: Categorization of content.
  - `rating`: Average viewer rating.
  - `description`: Brief summary of the content.
  - `stars`: Main cast members.
  - `votes`: Number of user votes.

## Data Wrangling Steps
To ensure data quality, the following cleaning and transformation steps were performed in `Wrangling.ipynb`:
1. **Handling Missing Values**: 
   - `certificate` and `genre` were filled with "Unknown".
   - `duration` was filled with the mode.
   - `rating` was filled with the mean.
   - `votes` was filled with the median.
   - Rows with missing `year` values were dropped.
2. **Data Type Correction**:
   - Extracted numerical years from strings.
   - Converted `duration` and `votes` to numerical formats.
3. **Feature Engineering**:
   - `rating_category`: Categorized ratings into 'Excellent' (>=8), 'Good' (>=6), and 'Average'.
   - `main_genre`: Extracted the primary genre for simplified analysis.
   - `popularity`: Created a score based on `rating * votes`.
4. **Filtering**:
   - Restricted analysis to content released after the year **2000**.
   - Removed outliers/low-engagement content by keeping only titles with more than **1000 votes**.

## Visualizations & Insights
The analysis includes several key visualizations to tell the story of the data:
- **Top 10 Genres**: Identification of the most common genres on the platform.
- **Rating Distribution**: A pie chart showing the percentage of content in different rating categories.
- **Rating Histogram**: Showing how ratings are distributed across all titles.
- **Duration vs. Rating**: A scatter plot analyzing if longer content leads to higher or lower ratings.
- **Yearly Trends**: A line plot showing how average ratings have changed over the last two decades.

## How to Run
1. Ensure you have Python installed with `pandas`, `numpy`, `matplotlib`, and `seaborn`.
2. Open `Wrangling.ipynb` in a Jupyter environment.
3. Run all cells to see the cleaning process and generated plots.

---
**Team Members**: Aarush Gupta, Kashish, Mannat Bansal
**Course**: Foundations of Data Science - SEM 2