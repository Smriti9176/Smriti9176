# 🧠 Data Analytics 

Welcome to my Data Analytics repository! This space is dedicated to showcasing the practical work, projects, and exercises I've completed throughout the course. It includes hands-on examples of data analysis, visualization, problem-solving, and code written in Python and Jupyter Notebooks.

---

## 📚 Tools Used

- **Python** for data processing and scripting
- **Jupyter Notebooks** for exploratory data analysis and reporting
- **Pandas & NumPy** for working with structured data
- **Matplotlib** for data visualization
- **SQL** for querying databases 
- **Git & GitHub** for version control and collaboration

---

## 🗂️ Project Description

- **IMDB_Movie_ratings**

## 🎯 Objective:
This project aimed to scrape, clean, and preprocess movie rating data from IMDb’s Top 250 movies list. The final output is a structured dataset ready for analysis or visualization.

---

## 🛠️ Tools Used:
- **Python 3**
- **Requests** – to fetch IMDb page
- **BeautifulSoup (bs4)** – for HTML parsing
- **Pandas** – for data manipulation
- **Regex (re)** – for formatting durations and genres

---

## 🔄 Process Summary:

1. **Scraping**  
   - Retrieved IMDb Top 250 data using the `requests` library and parsed it with `BeautifulSoup`.
   - Bypassed bot detection by including a custom **user-agent header** in the HTTP request.
   - Extracted movie data from embedded JSON (<script type="application/ld+json">), allowing for a more structured and complete dataset.

2. **Cleaning**  
   - Checked for and handled missing values.
   - Removed duplicates.
   - Standardized and cleaned textual fields.

3. **Preprocessing**
   - Converted ISO 8601 duration (e.g., `PT2H32M`) into both `Duration_Minutes` and a readable format like `2H 32M`.

---

## 🚧 Challenges & Solutions:

| Challenge | Solution |
|----------|-----------|
| IMDb blocked requests due to scraping (HTTP 430) | **Used headers with a user-agent** to mimic a real browser and bypass restrictions:  
```python
headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36'
}
requests.get(url, headers=headers)
``` |
| Difficulty parsing the HTML table for titles/ratings | Switched to parsing the embedded JSON data inside `<script type="application/ld+json">` |
| Duration field in ISO format (`PT2H30M`) | Used regex to extract minutes, then converted to both readable and numeric formats |

---

## 📁 Output:

- Final cleaned dataset: `IMDb_Final_Dataset.csv`
- Columns include: Title, Rating, Genre, Duration_Minutes, URL, Description, etc.
- Final dataset is ready for EDA, visualization, or modeling.

