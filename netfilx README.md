# 🎬 Netflix Data Analysis using Python + SQL

This project focuses on exploring the Netflix Movies and TV Shows dataset using Python and SQLite. The goal is to extract meaningful insights about the content available on Netflix based on type, country, release year, genres, and more.

---

## 📂 Dataset

- **Source**: [Netflix Movies and TV Shows on Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)
- **File Used**: `netflix_titles.csv`
- **Size**: ~3.4 MB

---

## 🔧 Tools & Technologies Used

- Python
- SQLite (in-memory database)
- Pandas
- Matplotlib

---

## 📊 Key Insights Extracted

- Total number of Movies vs TV Shows
- Year-wise content trend on Netflix
- Top 5 countries with the most Netflix content
- Top 5 directors with the most contributions
- Most common genres/categories

---

## 🧠 Sample SQL Queries Used

```sql
-- Total Movies vs TV Shows
SELECT type, COUNT(*) AS total FROM netflix GROUP BY type;

-- Year-wise content added
SELECT release_year, COUNT(*) AS total FROM netflix GROUP BY release_year ORDER BY release_year DESC;

-- Top 5 Countries
SELECT country, COUNT(*) AS total FROM netflix WHERE country IS NOT NULL GROUP BY country ORDER BY total DESC LIMIT 5;

-- Top 5 Directors
SELECT director, COUNT(*) AS total FROM netflix WHERE director IS NOT NULL GROUP BY director ORDER BY total DESC LIMIT 5;

-- Common Genres
SELECT listed_in, COUNT(*) AS total FROM netflix GROUP BY listed_in ORDER BY total DESC LIMIT 10;
