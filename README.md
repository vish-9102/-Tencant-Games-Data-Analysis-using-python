# -Tencant-Games-Data-Analysis-using-python
Game Sales Analytics Project
A Data-Driven Exploration Using Python, Pandas, Matplotlib & Seaborn
📌 Project Overview

This project focuses on analyzing video game sales data to understand how the Top 5 Publishers perform across various gaming platforms. Using Python’s data analytics and visualization tools, the project uncovers trends such as platform dominance, publisher strengths, diversified strategies, and opportunities for market expansion.

The goal is to convert raw sales data into clear insights that support strategic decisions related to product development, marketing, platform focus, and revenue forecasting.

🛠️ Key Operations & Commands Executed

Below are the core operations implemented using Python, Pandas, Matplotlib, and Seaborn.

### 1️⃣ Data Loading & Cleaning
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("games.csv")
df.dropna(inplace=True)

### 2️⃣ Filtering Top 5 Publishers
top_publishers = df["Publisher"].value_counts().head(5).index
top_5_data = df[df["Publisher"].isin(top_publishers)]

### 3️⃣ Countplot: Publisher vs Platform
sns.countplot(data=top_5_data, x="Publisher", hue="Platform")
plt.xticks(rotation=45)
plt.show()

### 4️⃣ Crosstab: Publisher vs Platform
df_stacked_plot = pd.crosstab(
    index=top_5_data["Publisher"],
    columns=top_5_data["Platform"]
)
print(df_stacked_plot)

### 5️⃣ Stacked Bar Chart
df_stacked_plot.plot(kind="bar", stacked=True, figsize=(10,6))
plt.xticks(rotation=45)
plt.show()

### 6️⃣ Statistical Summaries
top_5_data.describe(include="all")

🔍 Vital Insights Gathered From the Analysis
📌 Platform Concentration

Many publishers focus heavily on specific gaming platforms, showing clear investment patterns.

📌 Publisher Dominance

A few publishers release significantly more games, indicating greater influence in the market.

📌 Uneven Market Spread

Some publishers spread their releases widely across platforms, while others focus on just a few.

📌 Platform Popularity Trends

Older consoles continue to perform well, showing:

High legacy value

Strong customer loyalty

Steady long-term performance

📌 Growth Opportunities

Publishers with limited platform diversity have potential to expand and reach new markets.

📈 Business Impact of the Findings
✔ Strategic Planning

Companies can identify which platforms deserve higher priority for game releases.

✔ Marketing Optimization

Marketing budgets can be directed toward platforms with higher publisher presence.

✔ Revenue Forecasting

Publisher-platform trends help predict future sales and market behavior.

✔ Market Expansion

Low-activity publishers on trending platforms (PC, PS5, Switch) can expand to capture more revenue.

✔ Operational Efficiency

Retailers and distributors can optimize:

Inventory

Stock distribution

Region-based platform demand



