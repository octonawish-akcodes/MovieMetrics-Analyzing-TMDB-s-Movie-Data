# MovieMetrics-Analyzing-TMDB-s-Movie-Data

This project analyzes the **TMDB Movies Dataset**, which contains information about 10,000 movies extracted from [TMDB](https://www.themoviedb.org/). The dataset includes details like user ratings, revenue, budget, genres, cast, and more. The goal of this project is to explore key questions about the movie industry and perform exploratory data analysis (EDA) on the dataset.

## Dataset Description
This dataset contains information about 10,000 movies, covering data from 1960 to 2015. The data includes various metrics, such as popularity, budget, revenue, user ratings, genres, and more. The original data was sourced from [Kaggle](https://www.kaggle.com/tmdb/tmdb-movie-metadata).

---

## Columns Description

| Column               | Description                                                             |
|----------------------|-------------------------------------------------------------------------|
| `id`, `imdb_id`      | Unique movie ID or IMDb ID                                              |
| `popularity`         | Popularity metric of the movie                                          |
| `budget`             | Total budget of the movie in USD                                        |
| `revenue`            | Total revenue of the movie in USD                                       |
| `original_title`     | Original title of the movie                                             |
| `cast`               | Names of the cast, separated by "|"                                     |
| `homepage`           | Movie's homepage URL (if available)                                     |
| `director`           | Director(s) of the movie (separated by "|")                             |
| `tagline`            | Catchphrase describing the movie                                        |
| `keywords`           | Keywords related to the movie                                           |
| `overview`           | Summary of the movie's plot                                            |
| `runtime`            | Total runtime of the movie in minutes                                   |
| `genres`             | Movie genres, separated by "|"                                          |
| `production_companies`| Movie's production company(s)                                           |
| `release_date`       | Release date of the movie                                               |
| `vote_count`         | Number of votes the movie has received                                  |
| `vote_average`       | Average user rating of the movie                                        |
| `release_year`       | Year of the movie's release (from 1960 to 2015)                         |
| `budget_adj`         | Budget adjusted for inflation (in terms of 2010 dollars)                |
| `revenue_adj`        | Revenue adjusted for inflation (in terms of 2010 dollars)               |

---

## Questions for Analysis

The analysis aims to answer the following questions:
1. **Do movies with high popularity achieve high revenue?**
2. **What are the most filmed genres in this dataset?**
3. **Is there a correlation between a movie's budget and its revenue?**

---

## Data Wrangling

The data can be found in the `tmdb-movies.csv` file, which is an edited version of the original Kaggle [TMDB 5000 Movie Dataset](https://www.kaggle.com/tmdb/tmdb-movie-metadata) used in the Udacity Data Analyst Nanodegree program.

---

## Data Cleaning

### Main Observations:
1. The dataset originally consisted of **10,866 rows** and **21 columns**.
2. One duplicate row was found and dropped.
3. Some columns were irrelevant to answering the analysis questions and were dropped.
4. Columns with missing values were handled appropriately.
5. `cast`, `director`, and `genres` contained values separated by "|", which were split into separate lists.
6. The `release_date` column was converted to a date format.
7. A new column for `profit` was added, calculated as:  
   ```python
   profit = revenue - budget
   ```
8. The `vote_average` was converted to a categorical variable based on rating ranges.
9. The `profit` column was categorized for better visualization and exploration.

---

## Exploratory Data Analysis (EDA)

After data cleaning, the dataset now contains **10,840 records** and **10 relevant columns**. The data is now free of duplicates and missing values, and the data types are consistent with the questions we intend to answer.

### Insights:

**Q1: Do movies with high popularity achieve high revenue?**
- High-popularity movies tend to generate significantly more revenue than lower-popularity movies.

**Q2: What are the most filmed genres in this dataset?**
- The most filmed genres are:
  - **Drama** (22.6% of movies)
  - **Comedy**
  - **Action**

**Q3: Is there a correlation between a movie's budget and its revenue?**
- There is a positive correlation between **budget** and **revenue**, indicating that higher-budget movies generally generate more revenue, with only a few outliers.

---

## Built with

This project was developed using the following tools:
- **JupyterLab**
- **Python 3**
- **Pandas**
- **NumPy**

---

## Flowchart

Below is the flowchart of the overall analysis process:

```plaintext
   +----------------------+
   |   Dataset Loading    |
   +----------------------+
            |
            v
   +----------------------+
   |   Data Cleaning      |
   +----------------------+
   | - Handle missing data|
   | - Drop irrelevant columns|
   | - Adjust data types  |
   +----------------------+
            |
            v
   +----------------------+
   |  Data Wrangling      |
   +----------------------+
   | - Create new columns |
   | - Split multi-valued columns |
   +----------------------+
            |
            v
   +----------------------+
   |   Exploratory Data   |
   |   Analysis (EDA)     |
   +----------------------+
            |
            v
   +----------------------+
   |   Visualization      |
   |   & Insights         |
   +----------------------+
            |
            v
   +----------------------+
   |  Answer Analysis Qs  |
   +----------------------+
```

This flowchart summarizes the steps taken from loading the data, through data cleaning and wrangling, to performing EDA and ultimately answering the analysis questions with insights and visualizations.

---

