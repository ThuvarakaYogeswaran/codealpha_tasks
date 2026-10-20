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
- [Tools & Libraries](#️-tools--libraries)
- [Key Findings Summary](#-key-findings-summary)
- [Author](#-author)

---

## 🔍 Overview

| Task | Topic | Dataset | Tools |
|------|-------|---------|-------|
| **Task 2** | Exploratory Data Analysis | Titanic (891 rows × 12 cols) | pandas, seaborn, scipy |
| **Task 3** | Data Visualization | Titanic | matplotlib, seaborn |
| **Task 4** | Sentiment Analysis | Tweets / Reviews (NLP) | NLTK VADER, wordcloud |

---

## 📊 Task 2 — Exploratory Data Analysis (EDA)

**Objective:** Understand the Titanic dataset structure, detect missing data, analyze distributions, test hypotheses, and uncover patterns in survival.

### 🧹 Data Cleaning

| Column | Issue | Action |
|--------|-------|--------|
| `Cabin` | 77.1% missing | Dropped, replaced with `HasCabin` flag |
| `Age` | 19.9% missing | Median imputation |
| `Embarked` | 0.2% missing | Mode imputation |
| Duplicates | None | — |

### 🖼️ Key Visuals

**Missing Values Heatmap**
![Missing Values](Task%202/images/01_missing_values.png)

**Distribution of Fare (right-skewed, log-transform recommended)**
![Fare Distribution](Task%202/images/02_dist_Fare.png)

**Correlation Heatmap**
![Correlation](Task%202/images/04_correlation_heatmap.png)

**Survival Rate by Category**
![Survival by Category](Task%202/images/05_survival_by_category.png)

### 📈 Statistical Tests

| Test | Statistic | p-value | Conclusion |
|------|-----------|---------|------------|
| Chi-square (Sex × Survived) | χ² = 260.72 | 1.20e-58 | ✅ Sex strongly associated with survival |
| Chi-square (Pclass × Survived) | χ² = 102.89 | 4.55e-23 | ✅ Class strongly associated |
| T-test (Fare by Survival) | t = 6.84 | 2.70e-11 | ✅ Survivors paid more |
| T-test (Age by Survival) | t = −1.90 | 0.058 | ❌ Not significant at 5% |

---

## 🎨 Task 3 — Data Visualization

**Objective:** Transform the Titanic dataset into clear, story-driven visuals that communicate insights instantly.

### 🖼️ Gallery

**1. Overall Survival Rate (Donut)**
![Survival Donut](Task%203/images/01_survival_donut.png)

**2. Survival by Class & Sex**
![Survival by Class Sex](Task%203/images/02_survival_by_class_sex.png)

**3. Age Distribution by Survival**
![Age Distribution](Task%203/images/03_age_distribution.png)

**4. Survival by Age Group**
![Age Group](Task%203/images/04_survival_by_age_group.png)

**5. Fare Distribution by Class**
![Fare by Class](Task%203/images/05_fare_by_class.png)

**6. Survival by Family Size**
![Family Size](Task%203/images/06_family_size.png)

**7. Correlation Heatmap (Focused)**
![Correlation](Task%203/images/07_correlation.png)

**8. Survival by Embarkation Port**
![Embarked](Task%203/images/08_embarked_survival.png)

**9. Dashboard — Executive Summary**
![Dashboard](Task%203/images/09_dashboard.png)

---

## 💬 Task 4 — Sentiment Analysis

**Objective:** Apply NLP (VADER lexicon) to classify text as Positive, Neutral, or Negative, then visualize patterns.

### 🧠 Method
- **Lexicon-based analysis** via NLTK VADER
- Compound score rules: `≥ +0.05` → **Positive**, `≤ −0.05` → **Negative**, otherwise → **Neutral**

### 🖼️ Gallery

**1. Sentiment Distribution (Donut)**
![Sentiment Donut](Task%204/images/01_sentiment_donut.png)

**2. Sentiment Count**
![Sentiment Count](Task%204/images/02_sentiment_count.png)

**3. Compound Score Distribution**
![Compound Distribution](Task%204/images/03_compound_distribution.png)

**4. Positive Word Cloud**
![Positive WordCloud](Task%204/images/04_wordcloud_positive.png)

**5. Negative Word Cloud**
![Negative WordCloud](Task%204/images/05_wordcloud_negative.png)

**6. Top Words per Sentiment**
![Top Words](Task%204/images/06_top_words.png)

**7. Component Scores**
![Component Scores](Task%204/images/07_component_scores.png)

**8. Text Length by Sentiment**
![Length by Sentiment](Task%204/images/08_length_by_sentiment.png)

**9. Dashboard**
![Sentiment Dashboard](Task%204/images/09_dashboard.png)

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

## 👤 Author

**[Your Name]**
Data Analytics Intern — CodeAlpha
🐙 [GitHub](https://github.com/ThuvaraKAyogeswaran)

---

## 🙏 Acknowledgements

- **CodeAlpha** for the internship opportunity and task structure
- **Titanic dataset** — publicly available on [Kaggle](https://www.kaggle.com/c/titanic)
- **VADER sentiment lexicon** — Hutto & Gilbert (2014)
