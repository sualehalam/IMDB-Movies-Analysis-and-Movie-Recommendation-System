# IMDB Analysis and Movies Recommendation System

<img width="1400" height="700" alt="image" src="https://github.com/user-attachments/assets/298ab2fe-f71b-49bb-a092-a47ddcbf3588" />

## Introduction

### Database Schema:

The movie dataset, which is originally from Kaggle, was cleaned and provided by Udacity. This data set contains information about 5,000 movies collected from The Movie Database (TMDb) and the whole dataset duration covers from 1960 to 2015. Contains data such as `title, cast, director, runtime, budget, revenue, release year` etc. 
- Certain columns, like `‘cast’` and `‘genres’`, contain multiple values separated by pipe (|) characters.
- There are some odd characters in the `‘cast’` column. Nothing to care much of, I leave them as is.
- The final two columns ending with `“_adj"` show the budget and revenue of the associated movie in terms of 2010 dollars, accounting for inflation over time.

## Research Questions for Analysis
 1. What were the Top 5 Genres throughout the years?
 2. How did the amount of movies produced changed over time?
 3. What is the Average Running Time Of All the Movies?
 4. How does the budget changes throughout the years?
 5. What should be an appropriate budget for a movie to succeed?


## Authors

* **Sualeh Alam** - [SualehAlam](https://github.com/sualehalam) 

## License 

![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)
