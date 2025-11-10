# IMDB Analysis & Movies Recommendation System

<img width="1400" height="700" alt="image" src="https://github.com/user-attachments/assets/298ab2fe-f71b-49bb-a092-a47ddcbf3588" />

## Introduction
A data science and machine learning project exploring the **IMDB (Internet Movie Database)** dataset to analyze movie trends, build predictive models, create a content-based movie recommendation system. and visualize film keywords through word clouds.


### Dataset Schema:

The movie dataset, which is originally from **[Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata),** was cleaned and provided by Udacity. This data set contains information about 5,000 movies collected from The Movie Database (TMDb) and the whole dataset duration covers from 1960 to 2015. Contains data such as `title, cast, director, runtime, budget, revenue, release year` etc. 
- Certain columns, like `‘cast’` and `‘genres’`, contain multiple values separated by pipe (|) characters.
- There are some odd characters in the `‘cast’` column. Nothing to care much of, I leave them as is.
- The final two columns ending with `“_adj"` show the budget and revenue of the associated movie in terms of 2010 dollars, accounting for inflation over time.

##  Project Workflow:

1. **Data Preprocessing** – Cleaned the dataset (handled NaN values, parsed genres, normalized columns).
2. **Exploratory Data Analysis** – Identified trends, top genres, budgets, and durations.
3. **Modeling** – Built linear regression models to analyze patterns (movies/year, popularity vs budget).
4. **Recommendations** – Implemented:
   - Keyword-based recommender (_content similarity_)
   - Fuzzy title-based recommender (_string matching_)
5. **Visualization** – Created movie word clouds and plotted key insights.

## Research Questions for Analysis
 1. What were the Top 5 Genres throughout the years?
 2. How did the amount of movies produced changed over time?
 3. What is the Average Running Time Of All the Movies?
 4. How does the budget changes throughout the years?
 5. What should be an appropriate budget for a movie to succeed?


## 📈 Linear Regression Models

### 🔹 Model 1: Predicting Number of Movies per Year

**Objective:** Predict the **total number of movies** produced each **year**.  
- **Input Feature:** Year  
- **Output:** Number of movies released  

**Model:** `LinearRegression()` from `sklearn.linear_model`

**Example Prediction Result:**
- Predicted movies in 2020: **~327**
- Actual movies released (Google data): **329**

**Model Remarks:**
The model showed excellent predictive accuracy, by predicting total movies produced in the future with **99%** accuracy.

### 🔹 Model 2: Predicting Movie Popularity Score Based on Budget

**Objective:** Predict movie **popularity score** using its **budget**.  
- **Train/Test Split:** 70% / 30%
- **Input:** Budget  
- **Output:** Popularity

**Model:** `LinearRegression()` from `sklearn.linear_model`

**Example Prediction Result:**
> For a movie with a $280 million budget, predicted popularity score ≈ **6.0**

**Model Remarks:**
This model helps estimate how budget influences potential popularity of a particular movie.

## Movie Recommendation Systems

This project features **two** different movie recommendation techniques: one that finds movies with _similar_ content using _keywords_, and another that matches movie titles based on _text similarity_.

### 1️. Keyword-Based Recommendation System

**Goal:** Recommend similar movies based on shared keywords (themes, genres, plots).

**Technique:**
- Extract keywords for each movie.
- Split keyword strings into multiple fields.
- Compare selected movie keywords with others.
- Recommend top 5 matching titles.

**Example:**
> Input Movie: **Terminator Genisys**  
> **Top 5 Recommendations:**
> - Interstellar  
> - Terminator Salvation  
> - Megamind  
> - Justice League: Crisis on Two Earths  
> - The Matrix

**Recommendation Algorithm Remarks:**

This recommendation provides remarkable content-based movies recommendation using keyword matching.

---

### 2. Fuzzy Matching Movie Recommender

**Goal:** Suggest movies with titles similar to the user’s input (string similarity).

**Technique:**
- Uses `fuzzywuzzy` library for finding partial string matching score.
- Recommends movies whose titles have ≥**90%** similarity score.

**Example Input:**
> `"Furious"`

> **Output Suggestions:**
> - Furious 7  
> - Fast & Furious  
> - The Fast and the Furious  
> - Fast & Furious 6  
> - 2 Fast 2 Furious  

**Recommendation Algorithm Remarks:**

This recommendation technique allows flexible movie title matching even with typos or partial inputs.

---

## Word Cloud Visualization

To better understand the most common keywords and themes in the movie dataset,  a **Word Cloud** was generated from the movie keywords.  

This visualization highlights the most frequently occurring movie-related terms — _bigger words indicate more frequent appearances_.

### Movie Keyword Word Cloud for movie Spectre (2015)

<img width="300" height="540" alt="spectre" src="https://github.com/user-attachments/assets/7644d75c-3a97-4117-b6be-b9006c20fd3e" />

---


## Conclusion

- The first research question **"What were the Top 5 Genres throughout the years?"** has shown useful results, as the most popular genre turned out to be **Drama**. Perhaps it is because Adventure and Science Fiction movies are more expensive to produce so they are more rarely made than **Drama, Comedy, Thriller**. Believe it or not, this data could be extremey useful for the 'Production Companies', because now they know which type of movies tend to be more popular among the masses and this could help them to drive more potential customers and eventually more sales. 

- The second research question **"How did the amount of movies produced changed over time?"** gave a well defined increasing trend for movies released. The graph also shows that a peak was attained in the year 2011 for the most movies released. Also, according to Wikipedia, **Film critic Scout Tafoya considers 2011 as the best year for cinema.** 

- The third research question **"What is the Average Running Time Of All the Movies?"** shows an accurate result of approximately 106 minutes. This is also evident from the histogram which is plotted against Running Time and Number Of Movies.

- The fourth research question **"How does the budget changes throughout the years?"** shows quite useful results to the users because users can observe that throughout the years the budget has been increasing throughout the years and suddenly skyrockets in the year 2011, which is considered as the best year for cinema according to Wikipedia. In 2011, **Pirates of the Caribbean: On Stranger Tides** is the maximum budget movie till this day, with a maximum budget of 380 Million Dollars USD.

- The fifth research question **"What should be an appropriate budget for a movie to succeed?"** has shown surprising results. Some useful deductions which are clearly evident from the graph are it's not necessary for a movie to become popular and succeed even if it has a higher budget and vice versa.

## Limitation:
1. Many entries which contained _null (NaN)_ values had been removed from the dataset, so the size of the dataset has been significantly reduced and this will greatly affect the accuracy of our results.
2. The results obtained from our linear regression model using budget for predicting movies popularity score is only done for educational purposes only and in reality many other external factors affect movies popularity like Time of Release, Marketing, Cast of Movie, Storyline, and many more.

## Future Work:
1. Create a web dashboard using Streamlit or Flask.
2. Expand dataset with post-2015 movies for an updated movie analysis.
3. Add model evaluation metrics ($R^2$, MAE) for deeper insights.


## Authors

 [![](https://img.shields.io/badge/LinkedIn-%40Sualeh%20Alam-lightgrey?colorA=abcdef&logo=data:image/jpeg;base64,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)](https://www.linkedin.com/in/sualeh-alam/)
 
## License 

![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)
