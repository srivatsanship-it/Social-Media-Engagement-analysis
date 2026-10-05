# Social Media Engagement Analytics

End-to-end exploratory analysis of 5,000 social media posts using Python (Pandas, NumPy, Matplotlib, Seaborn, Plotly, SciPy). Built as the module-end assignment for *Python for Data Analysis*.

## Project Overview

Social platforms generate large volumes of engagement data. This project cleans and explores that data to answer questions about content performance, user trends, behaviour and sentiment.

## Dataset

`social_media_engagement_5000.csv` has 5,000 posts and 19 columns, covering Jan 2022 to Dec 2023 across 10 countries.

| Group | Columns |
|---|---|
| User | `user_id`, `age`, `gender`, `country`, `follower_count`, `is_verified` |
| Post | `post_id`, `post_type`, `post_category`, `hashtags`, `posted_at`, `device_type` |
| Engagement | `likes`, `comments`, `shares`, `watch_time_sec`, `impression_count`, `engagement_rate`, `sentiment` |

## Repository Contents

| File | Description |
|---|---|
| `Social_Media_Engagement_Analytics.ipynb` | Full notebook: code, outputs, 18 visualisations and explanations |
| `Summary_Social_Media_Engagement.pdf` | One-page summary of findings |
| `social_media_engagement_5000.csv` | Source dataset |

## What the Notebook Covers

1. **Import & setup:** load the CSV, check data types, convert `posted_at` to datetime (`dd-mm-yyyy`).
2. **Data cleaning:** impute 150 missing values in each of six columns (median/mode; median by post type for likes, comments and shares; "unknown" kept for sentiment), check duplicates, standardise categories, cap impossible values, extract hashtag count.
3. **Exploration:** `head`/`tail`/`info`/`describe`, value counts, correlation matrix, groupby summaries.
4. **Wrangling:** engagement score, weighted score, log transforms, date and age-group features, `merge` and `concat`.
5. **Statistics:** mean, median, mode, std, variance, percentiles, skewness and kurtosis, plus Kruskal-Wallis and Mann-Whitney tests.
6. **Visualisation:** 6 Matplotlib, 6 Seaborn and 6 interactive Plotly charts.
7. **Insights:** answers to every question in the brief.

## Key Findings

- **No group difference is statistically significant** (all p-values above 0.05). Post type, category, country, age, device and sentiment differ by only a few percent.
- **Post type:** reels have the most interactions per post (about 11,981), with images a near tie.
- **Category:** music leads on interactions; education has the highest median engagement rate.
- **Verified accounts:** no reliable advantage (p = 0.09).
- **Device:** mobile has the highest watch time (about 4,088 s), but the gap is small.
- **Sentiment:** positive posts lead on interactions; neutral posts are lowest.
- **Time of day:** cannot be measured because `posted_at` contains only dates. Weekday and month were used as a proxy.

## Data Quality Notes

- 467 rows had likes, comments or shares above impressions; they were flagged and capped at the impression count.
- `engagement_rate` is highly skewed (median 0.25, mean 0.96, max 191), so rankings use the median.
- Nine `post_id` values repeat but belong to different posts, so they were kept.
- The metrics are close to uniformly distributed and uncorrelated, which suggests the data is synthetic.

## How to Run

**Google Colab**
1. Open [colab.research.google.com](https://colab.research.google.com) and upload the notebook (File, then Upload notebook).
2. Upload `social_media_engagement_5000.csv` using the Files panel on the left.
3. Choose Runtime, then Run all.

**Local Jupyter**
```bash
pip install pandas numpy matplotlib seaborn plotly scipy jupyter
jupyter notebook Social_Media_Engagement_Analytics.ipynb
```
Keep the notebook and the CSV in the same folder.

## Tools

Python 3, Pandas, NumPy, Matplotlib, Seaborn, Plotly, SciPy

## Author

Srivatsan
