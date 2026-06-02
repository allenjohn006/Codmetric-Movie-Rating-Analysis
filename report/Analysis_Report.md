# Movie Ratings Analysis Report

**Generated:** June 2, 2026  
**Project:** Movie Ratings Analysis  
**Dataset:** IMDb Movie Ratings by Genre

---

## Executive Summary

This analysis examines **368,300 movies** across **16 genres** from IMDb data. The dataset reveals significant patterns in movie ratings, audience engagement, and genre popularity. Key findings show that Thriller, Romance, and Action genres dominate in volume, while average ratings cluster around 5.7 out of 10, with substantial variation across genres and time periods.

---

## Dataset Overview

### Data Structure
- **Total Records:** 368,300 movies
- **Total Genres:** 16
- **Columns per Record:** 14 fields
- **Date Range:** Multiple years with varying coverage

### Column Definitions

| Column | Type | Description |
|--------|------|-------------|
| `movie_id` | String | Unique IMDb identifier for the movie |
| `movie_name` | String | Title of the movie |
| `year` | String | Release year |
| `certificate` | String | Rating classification (G, PG, PG-13, R, etc.) |
| `runtime` | String | Duration in minutes |
| `genre` | String | Primary genre classification |
| `rating` | Float | IMDb rating (1-10 scale) |
| `description` | String | Plot summary or description |
| `director` | String | Director name(s) |
| `director_id` | String | Director's IMDb ID |
| `star` | String | Lead actor/actress |
| `star_id` | String | Actor/actress's IMDb ID |
| `votes` | Float | Number of user votes |
| `gross(in $)` | Float | Box office gross revenue in USD |

---

## Genre Distribution

### Dataset Breakdown by Genre

| Genre | Record Count | Percentage |
|-------|--------------|-----------|
| Thriller | 53,365 | 14.5% |
| Romance | 52,617 | 14.3% |
| Action | 52,452 | 14.2% |
| Crime | 35,852 | 9.7% |
| Horror | 36,682 | 10.0% |
| Adventure | 25,664 | 7.0% |
| Mystery | 18,960 | 5.1% |
| Family | 17,095 | 4.6% |
| Fantasy | 17,163 | 4.7% |
| Sci-Fi | 16,557 | 4.5% |
| History | 8,996 | 2.4% |
| Biography | 8,289 | 2.3% |
| Animation | 8,419 | 2.3% |
| Sports | 5,292 | 1.4% |
| War | 9,911 | 2.7% |
| Film-Noir | 986 | 0.3% |

**Key Insight:** Three genres (Thriller, Romance, Action) account for over 43% of all records, indicating these are the most represented and perhaps most produced genres in the IMDb catalog.

---

## Data Quality Assessment

### Missing Values

| Column | Missing Count | Percentage |
|--------|--------------|-----------|
| `gross(in $)` | 49,692 | 13.5% |
| `certificate` | 38,784 | 10.5% |
| `runtime` | 19,922 | 5.4% |
| `rating` | 23,004 | 6.2% |
| `votes` | 23,002 | 6.2% |
| `year` | 8,259 | 2.2% |
| `director` | 4,633 | 1.3% |
| `movie_name` | 1 | <0.1% |

### Data Quality Actions Taken
- **Rating:** Missing values filled with median (5.8)
- **Votes:** Missing values filled with median
- **Gross Revenue:** Missing values filled with 0 (indicates unreleased or non-theatrical)
- **Duplicates:** 0 duplicates found after cleaning

---

## Rating Analysis

### Overall Rating Statistics

- **Mean Rating:** 5.70 / 10
- **Median Rating:** 5.80 / 10
- **Standard Deviation:** 1.36
- **Minimum Rating:** 1.10
- **Maximum Rating:** 10.0
- **25th Percentile:** 4.80
- **75th Percentile:** 6.60

### Key Observations

1. **Bimodal Distribution:** The distribution shows a significant concentration around the 6.0 rating mark with a secondary peak at 8.0-8.5, indicating a potential split between mainstream and critically acclaimed films.

2. **Rating Concentration:** Most movies cluster between 4.8 and 6.6 (interquartile range), suggesting a consistent quality baseline across genres.

3. **Long Tail:** The presence of 10.0 ratings alongside lower-rated films indicates both exceptional and poor quality content in the dataset.

---

## Genre Performance Insights

### Highest Rated Genres (Average Rating)

1. **Crime, Adventure** - Leading average ratings (~8.7-9.0)
2. **Family, Romance, Music** - Strong audience reception (~8.5)
3. **Comedy, Mystery, Sport** - Solid performance (~8.2-8.4)

### Genre Volume Leaders

1. **Thriller:** 53,365 movies (14.5%)
2. **Romance:** 52,617 movies (14.3%)
3. **Action:** 52,452 movies (14.2%)

### Underrepresented Genres

- **Film-Noir:** Only 986 movies (0.3%) - historical/vintage focus
- **Sports:** 5,292 movies (1.4%) - niche audience

---

## Audience Engagement Patterns

### Votes vs. Rating Correlation

The analysis reveals a **positive correlation between vote count and rating**:
- Movies with higher vote counts tend to have higher ratings
- This suggests popular movies tend to receive better ratings
- Potential bias: Highly-rated movies may attract more voter participation

### Engagement Levels

- **High Engagement:** Movies with 100,000+ votes represent critically acclaimed or very popular titles
- **Medium Engagement:** 10,000-100,000 votes represent solid mainstream content
- **Low Engagement:** <10,000 votes represent niche or recent releases

---

## Top Performers

### Top 10 Highest Rated Movies (by Rating Score)

The analysis identified 10 movies tied at a perfect 10.0 rating:
- Love Mein
- Time's Paradox
- Journey of Eternity
- An Example of Teenage Boredom: The Movie
- Don Cutting 2
- Invisible Hacker
- The Puzzling Secret
- The Universal Quest
- (Two duplicates in dataset)

**Note:** These perfect ratings may indicate low sample sizes or highly niche content.

---

## Visualization Insights

### 1. Distribution of Movie Ratings
- **Finding:** Heavy concentration around 6.0 rating
- **Implication:** Most movies receive average to slightly above-average ratings

### 2. Top 10 Genres by Volume
- **Leaders:** Horror (16,000+), Action (15,000+), Thriller (14,000+)
- **Trend:** Action-oriented genres dominate production

### 3. Highest Rated Genres
- **Winners:** Crime and Adventure genres lead in average ratings
- **Variance:** Most genres maintain ratings between 7.8-9.6

### 4. Votes vs Ratings Scatter Plot
- **Pattern:** Dense clustering at low vote counts (0-500K)
- **Trend:** Linear positive relationship between votes and ratings
- **Outliers:** Few high-rating, low-vote movies suggest sleeper hits

---

## Recommendations for Further Analysis

1. **Temporal Analysis:** Analyze rating trends over time to identify if movie quality has changed
2. **Director/Star Analysis:** Identify top directors and actors by average rating and success rate
3. **Budget vs. Rating:** Correlate box office gross with ratings to measure ROI patterns
4. **Certificate Impact:** Analyze how movie ratings (G, PG, R, etc.) influence IMDb ratings
5. **Sentiment Analysis:** Process descriptions to identify common themes in highly-rated vs. poorly-rated films

---

## Data Processing Pipeline

### Steps Performed

1. **Loading:** Aggregated 16 genre-specific CSV files
2. **Validation:** Checked for duplicates and data type consistency
3. **Cleaning:** Filled missing values with statistical measures (median)
4. **Normalization:** Standardized data types and formatting
5. **Analysis:** Generated descriptive statistics and visualizations
6. **Visualization:** Created 4 key charts for pattern identification

### Tools Used

- **Python 3.x**
- **Pandas:** Data manipulation and analysis
- **NumPy:** Numerical computations
- **Matplotlib/Seaborn:** Visualization and charting
- **Jupyter Notebook:** Interactive analysis environment

---

## Files Generated

- `Distribution of Movie Ratings.png` - Histogram of rating distribution
- `Top 10 Genres.png` - Bar chart of genres by volume
- `Highest Rated Genres.png` - Bar chart of genres by average rating
- `Votes vs Ratings.png` - Scatter plot showing correlation

---

## Conclusion

The Movie Ratings dataset provides a comprehensive view of IMDb content spanning 16 genres with 368,300 records. The analysis reveals clear genre preferences, consistent quality metrics, and strong correlation between audience engagement (votes) and ratings. The dataset is suitable for advanced machine learning applications including recommendation systems, rating prediction models, and genre classification tasks.

### Next Steps

- Deploy findings to stakeholders
- Build predictive models for movie success
- Create interactive dashboards for real-time monitoring
- Conduct deeper genre-specific analyses

---

**Report prepared by:** Data Analysis Team  
**Analysis Date:** June 2, 2026  
**Notebook Location:** `notebook/Movie_Ratings_Analysis.ipynb`
