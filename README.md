---

# The Algorithm of Success
A Data-Driven Investment Strategy for the Modern Film Industry
This project analyzes thousands of films using OMDb API data to uncover patterns that help investors and producers make data-driven decisions about movie investments. It studies the relationship between genre, critic scores, audience ratings, cast/crew, and box office revenue to identify financially resilient film strategies.
Built as a storytelling + analytics notebook combining data engineering, exploratory analysis, and strategic insight generation.

---

## Problem Statement
The film industry is noisy and high-risk. Critics, audience sentiment, genre trends, and star power all influence outcomes — but not equally.
This project answers:
- Which genres are financially safest?
- Do bad critic reviews really hurt revenue?
- When does audience opinion matter more than critics?
- Which genres are prestige vs profit plays?
- Does franchise talent outperform star power alone?

---

## Data Source
- Primary Source: OMDb API (Open Movie Database)
- The notebook:
- Takes a movie title list
- Queries OMDb API
- Enriches each title with structured metadata
- Fields Collected
- Box office revenue
- IMDb rating
- Rotten Tomatoes score
- Metacritic score
- Genre
- Year
- Country
- Awards & wins
- Actors
- Directors
- Runtime

---

## Project Pipeline (From Notebook)
**1.Data Collection — OMDb API Enrichment**
- API requests made per movie title
- JSON responses parsed
- Ratings extracted from nested structures
- Box office fields captured as strings



**2. Data Cleaning & Preprocessing**
- Drop failed API responses
- Convert box office strings → numeric values
- Parse ratings into separate columns:
- IMDb
- Rotten Tomatoes
- Metacritic
- Handle missing values
- Normalize genres (split multi-genre rows)
- Standardize year & country fields


 **3.Feature Engineering**
- The notebook creates derived metrics:
-  Rotten vs Fresh classification
-  Critic < 60% filter (“Rotten movies”)
-  Median revenue by genre
-  Critic − Audience score gap
-  Award win indicators
-  Actor & Director median box office (bankability)
-  Genre risk grouping
-  Yearly revenue aggregation


 **4.Exploratory Analysis**
- Key analyses performed:
- Revenue distribution by genre
- Median revenue of poorly reviewed films
- Critic vs audience opinion gap distribution
- Genre-wise critic vs audience disagreement
- Audience score vs revenue correlation
- Rotten movie survival analysis
- Talent bankability rankings
- Revenue trends over time

---

## Core Insights
**Teflon Genres**
- Action, Adventure, and Fantasy films remain financially strong even when critic scores are poor.
- Bad reviews do not significantly reduce their median revenue.

**Critic vs Audience Disconnect**
- A measurable opinion gap exists:
- Audience-favored genres → Action, Fantasy, Comedy
- Critic-favored genres → Documentary, History
- Audience score often predicts revenue better than critic score in commercial genres.

**Revenue Leaders**
- Top median box office genres:
- Action
- Adventure
- Animation
- These function as commercial safe zones.

**Prestige Strategy Risk**
- Drama & Biography dominate awards
- Oscar wins are rare (~8–9%)
- Failed prestige films have weak financial fallback
- Awards act as long-term value multipliers

**Franchise Talent Effect**
- Actors and directors tied to franchises show:
- Higher median film revenue
- Lower downside risk
- Repeat commercial performance
- Franchise ecosystem > standalone star power.

## Investment Strategies Proposed
**Strategy Alpha — Commercial Play**
- Goal: Revenue stability
- Genres: Action / Adventure / Animation
- Talent: Franchise-attached actors & directors
- Critic scores: Not decision drivers
- Marketing focus: Spectacle & scale

**Strategy Beta — Prestige Play**
- Goal: Awards & reputation
- Genres: Drama / Biography
- Talent: Auteur directors
- Critic reception: Critical
- Higher risk, prestige upside

---

## Tech Stack
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Requests
- Jupyter Notebook
- OMDb API

---

## How to Run
**Clone Repo**
- git clone <your-repo-url>
- cd <repo-name>
**Install Dependencies**
- pip install pandas numpy matplotlib seaborn requests jupyter
**Add OMDb API Key**
- Get key from OMDb and set:
- export OMDB_API_KEY=your_key_here
**Run Notebook**
- jupyter notebook
Open:
- Storytelling.ipynb

---

## Suggested Repo Structure
├── Storytelling.ipynb
├── Report.pdf
├── data/
│   └── enriched_movies.csv
├── figures/
├── README.md

---

## Limitations
- Uses gross box office, not ROI
- No production budget data
- API response gaps for some films
- Franchise detection inferred indirectly

---

## Future Extensions
- ROI modeling using production budgets
- Release seasonality analysis
- Streaming vs theatrical comparison
- Predictive revenue modeling
- Franchise graph clustering
