# 🎮 Steam Video-Game Market Analysis — Big Data with PySpark

> Large-scale analysis of **55,691 Steam games** with **PySpark on Databricks** to understand what makes a game popular, ahead of a new game launch.
> *Jedha Data Science certification project — RNCP35288, Block 2 (Big Data analysis with Spark).*

---

## 🎯 Business problem
Ubisoft is preparing a new game and wants to understand the video-game market on Steam:
- What does the market look like (publishers, genres, prices, release trends)?
- Which genres and platforms perform best?
- **Which factors are associated with popularity** (positive reviews) and sales (estimated owners)?

## 📊 Data
- **55,691 games** from the Steam store (JSON, stored on AWS S3)
- Nested and semi-structured fields: publisher, developer, release date, price, discount, owners range, positive/negative reviews, platforms, genres, categories, tags, languages, age rating…

## 🛠️ Approach (PySpark / Databricks)
- Reading semi-structured JSON from S3 and flattening nested fields (`explode`, `split`)
- Distributed aggregations for the market, genre and platform analyses
- Feature engineering, correlation matrix (`pyspark.ml.stat.Correlation`)
- Linear regression on standardised features (`VectorAssembler`, `StandardScaler`, `LinearRegression`)

## 🔍 Key insights
**Market overview**
- Release peak in **2021 (8,823 games)**, then 2022 (7,455)
- Average price **≈ $7.73**; only **4.5 %** of games are discounted
- Top publishers by number of games: Big Fish Games, 8floor, SEGA
- **Windows 99.97 %** of games · Mac 22.9 % · Linux 15.2 %

**Genres**
- Most common: Indie, Action, Casual
- Best review ratios: Casual (0.743), Indie (0.742), Adventure (0.739)
- Highest estimated average revenue: **Massively Multiplayer (~$4.1M per game)**, RPG (~$2.9M), Action (~$2.5M)

**Popularity drivers** (associations, not causal effects)
- **Number of supported languages has the strongest positive association** → localisation is a key lever
- Higher prices are associated with popularity, most likely because high-quality titles can charge more (reverse causality)
- Discounts and a large number of genres are slightly negatively associated with popularity

## 💡 Recommendations for the launch
- **Invest in localisation** (many languages) from day one
- Focus the positioning on a clear main genre rather than many genres
- Consider Mac/Linux support as a differentiator in a Windows-dominated market

## 🧰 Tech stack
`PySpark` · `Spark SQL` · `Spark MLlib` · `Databricks` · `AWS S3` · `Python`

## 📁 Repository
```
└── steam_analysis.ipynb   # full Databricks / PySpark analysis
```

---
👤 **Nouman Malidi Mlimi** — Data Scientist / Data Analyst · [Portfolio](https://noumanmalidi7.github.io) · [LinkedIn](https://www.linkedin.com/in/nouman-malidi-a99276326/)
