# CodeAlpha Data Analytics Internship — Projects

![CodeAlpha](https://img.shields.io/badge/CodeAlpha-Data%20Analytics-blue)
![Python](https://img.shields.io/badge/Python-3.10+-yellow)
![Status](https://img.shields.io/badge/Status-Completed-success)

This repository contains my submissions for the **CodeAlpha Data Analytics Internship**.
I completed **3 tasks** (minimum required: 2) covering exploratory data analysis,
data visualization, and sentiment analysis using Python.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Task 2 — Exploratory Data Analysis (EDA)](#-task-2--exploratory-data-analysis-eda)
- [Task 3 — Data Visualization](#-task-3--data-visualization)
- [Task 4 — Sentiment Analysis](#-task-4--sentiment-analysis)
- [Tools & Libraries](#-tools--libraries)
- [How to Run](#-how-to-run)
- [Key Findings Summary](#-key-findings-summary)
- [Author](#-author)

---

## 🔍 Overview

| Task | Topic | Dataset | Tools |
|------|-------|---------|-------|
| **Task 2** | Exploratory Data Analysis | Titanic (891 rows × 12 cols) | pandas, seaborn, scipy |
| **Task 3** | Data Visualization | Titanic | matplotlib, seaborn |
| **Task 4** | Sentiment Analysis | Tweets / Reviews (NLP) | NLTK VADER, wordcloud |

Each task contains:
- 📓 Python source code
- 🖼️ Saved charts (in `images/`)
- 📄 Insights documented in this README

---

## 📊 Task 2 — Exploratory Data Analysis (EDA)

**Objective:** Understand the Titanic dataset structure, detect missing data,
analyze distributions, test hypotheses, and uncover patterns in survival.

### 🧹 Data Cleaning
| Column | Issue | Action |
|--------|-------|--------|
| `Cabin` | 77.1% missing | Dropped, replaced with `HasCabin` flag |
| `Age` | 19.9% missing | Median imputation |
| `Embarked` | 0.2% missing | Mode imputation |
| Duplicates | None | — |

### 🖼️ Key Visuals

**Missing Values Heatmap**
![Missing Values](Task2/images/01_missing_values.png)

**Distribution of Fare (right-skewed, log-transform recommended)**
![Fare Distribution](task2/images/02_dist_Fare.png)

**Correlation Heatmap**
![Correlation](task2/images/04_correlation_heatmap.png)

**Survival Rate by Category**
![Survival by Category](task2/images/05_survival_by_category.png)

**Age & Fare Distribution by Survival**
![Age Fare by Survival](task2/images/06_age_fare_by_survival.png)

### 📈 Statistical Tests

| Test | Statistic | p-value | Conclusion |
|------|-----------|---------|------------|
| Chi-square (Sex × Survived) | χ² = 260.72 | 1.20e-58 | ✅ Sex strongly associated with survival |
| Chi-square (Pclass × Survived) | χ² = 102.89 | 4.55e-23 | ✅ Class strongly associated |
| T-test (Fare by Survival) | t = 6.84 | 2.70e-11 | ✅ Survivors paid more |
| T-test (Age by Survival) | t = −1.90 | 0.058 | ❌ Not significant at 5% |

### 🔑 Key Insights
1. **Sex** is the strongest predictor — 74% of women survived vs 19% of men.
2. **Pclass** matters — 1st class ≈ 63% survival, 3rd class ≈ 24%.
3. **Fare** is heavily right-skewed (skew = 4.79) — recommend log transform.
4. **HasCabin** correlates positively (r = +0.32) — wealth proxy.
5. **Age** is not a statistically significant predictor.

---

## 🎨 Task 3 — Data Visualization

**Objective:** Transform the Titanic dataset into clear, story-driven visuals
that communicate insights instantly.

### 🖼️ Gallery

**1. Overall Survival Rate (Donut)**
![Survival Donut](task3/images/01_survival_donut.png)

**2. Survival by Class & Sex**
![Survival by Class Sex](task3/images/02_survival_by_class_sex.png)

**3. Age Distribution by Survival**
![Age Distribution](task3/images/03_age_distribution.png)

**4. Survival by Age Group**
![Age Group](task3/images/04_survival_by_age_group.png)

**5. Fare Distribution by Class**
![Fare by Class](task3/images/05_fare_by_class.png)

**6. Survival by Family Size**
![Family Size](task3/images/06_family_size.png)

**7. Correlation Heatmap (Focused)**
![Correlation](task3/images/07_correlation.png)

**8. Survival by Embarkation Port**
![Embarked](task3/images/08_embarked_survival.png)

**9. Dashboard — Executive Summary**
![Dashboard](task3/images/09_dashboard.png)

### 🔑 Story Takeaways
1. **Sex gap is the headline** — 74% female vs 19% male survival.
2. **Class matters** — 1st class survived 3× more often than 3rd.
3. **Children (<12) had the highest survival** (~58%).
4. **Small families (2–4)** survived better than solo travelers.
5. **Cherbourg passengers** had the best survival rate (~55%).
6. **Higher fares = higher survival** — wealth proxy confirmed.

---

## 💬 Task 4 — Sentiment Analysis

**Objective:** Apply NLP (VADER lexicon) to classify text as Positive, Neutral,
or Negative, then visualize patterns.

### 🧠 Method
- **Lexicon-based analysis** via NLTK VADER
- Compound score rules:
  - `≥ +0.05` → **Positive**
  - `≤ −0.05` → **Negative**
  - Otherwise → **Neutral**

### 🖼️ Gallery

**1. Sentiment Distribution (Donut)**
![Sentiment Donut](task4_sentiment/images/01_sentiment_donut.png)

**2. Sentiment Count**
![Sentiment Count](task4/images/02_sentiment_count.png)

**3. Compound Score Distribution**
![Compound Distribution](task4/images/03_compound_distribution.png)

**4. Positive Word Cloud**
![Positive WordCloud](task4/images/04_wordcloud_positive.png)

**5. Negative Word Cloud**
![Negative WordCloud](task4/images/05_wordcloud_negative.png)

**6. Top Words per Sentiment**
![Top Words](task4/images/06_top_words.png)

**7. Component Scores**
![Component Scores](task4/images/07_component_scores.png)

**8. Text Length by Sentiment**
![Length by Sentiment](task4/images/08_length_by_sentiment.png)

**9. Dashboard**
![Sentiment Dashboard](task4/images/09_dashboard.png)

### 🔑 Key Insights
1. Sentiment distribution reveals the overall tone of the dataset.
2. Positive texts cluster near compound = **+0.6 to +1.0**.
3. Negative texts cluster near compound = **−0.6 to −1.0**.
4. **Positive word themes:** love, great, amazing, best, excellent.
5. **Negative word themes:** worst, terrible, disappointed, bad, refund.
6. **Text length does NOT correlate** strongly with sentiment polarity.
7. **Business value:** Use sentiment trends to guide customer service,
   product quality, and marketing tone.

---

## 🛠️ Tools & Libraries

| Category | Tools |
|----------|-------|
| **Language** | Python 3.10+ |
| **Data** | pandas, numpy |
| **Visualization** | matplotlib, seaborn, wordcloud |
| **Statistics** | scipy.stats |
| **NLP** | NLTK (VADER), re (regex) |

---
