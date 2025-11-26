# -Tencant-Games-Data-Analysis-using-python
🎮 Game Sales Analytics Project
A Data-Driven Exploration Using Python, Pandas, Matplotlib & Seaborn
📌 Project Overview

This project focuses on analyzing video game sales data to understand how the Top 5 Publishers perform across various gaming platforms. Using Python’s data analytics and visualization libraries, the project uncovers trends, patterns, and relationships that highlight platform dominance, publisher strengths, and potential areas for market expansion.

The goal is to convert raw sales data into clear insights that support business decisions related to product strategy, platform focus, marketing, and budgeting.

🛠️ Key Operations & Commands Executed
1️⃣ Data Loading & Cleaning
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("games.csv")
df.dropna(inplace=True)

2️⃣ Filtering Top 5 Publishers
top_publishers = df["Publisher"].value_counts().head(5).index
top_5_data = df[df["Publisher"].isin(top_publishers)]

3️⃣ Countplot: Publisher vs Platform
sns.countplot(data=top_5_data, x="Publisher", hue="Platform")
plt.xticks(rotation=45)
plt.show()

4️⃣ Crosstab: Publisher vs Platform
df_stacked_plot = pd.crosstab(
    index=top_5_data["Publisher"],
    columns=top_5_data["Platform"]
)
print(df_stacked_plot)

5️⃣ Stacked Bar Chart
df_stacked_plot.plot(kind="bar", stacked=True, figsize=(10,6))
plt.xticks(rotation=45)
plt.show()

6️⃣ Statistical Summaries
top_5_data.describe(include="all")

🔍 Vital Insights Gathered From the Analysis
📌 Platform Concentration

Many publishers focus heavily on specific platforms (e.g., PlayStation, Xbox), showing loyal user bases and long-term investment.

📌 Publisher Dominance

A few publishers lead significantly in total game count, indicating strong market control and frequent releases.

📌 Uneven Market Spread

Some publishers diversify across numerous platforms, while others concentrate on a limited set — reflecting different business strategies.

📌 Platform Popularity Trends

Older platforms still have a high number of releases, indicating:

Strong legacy value

Loyal gamer communities

Long-term profitability for certain game categories

📌 Potential Growth Opportunities

Publishers with low presence on newer platforms have potential to expand and tap new market segments.

📈 Business Impact of the Findings
✔ Strategic Planning

Publishers can identify which platforms deserve more development and release priority.

✔ Marketing Optimization

Campaigns can be targeted to platforms with higher user engagement and game volume.

✔ Revenue Forecasting

Platform-wise trends help estimate:

Future sales

Market growth or decline

Financial viability

✔ Market Expansion

Publishers with minimal activity on trending platforms (PC, PS5, Switch, etc.) can explore new audience segments.

✔ Operational Efficiency

Retailers and distributors can optimize:

Inventory planning

Region-specific platform stock

Distribution strategies

I



