# -Tencant-Games-Data-Analysis-using-python
Game Sales Analytics Project
A Data-Driven Exploration Using Python, Pandas, Matplotlib & Seaborn
📌 Project Overview

This project focuses on analyzing video game sales data to understand how the Top 5 Publishers perform across various gaming platforms. Using Python’s analytics and visualization tools, the analysis uncovers trends such as platform dominance, publisher strengths, diversified strategies, and opportunities for market expansion.

The goal is to transform raw data into clear insights that help support strategic decisions related to product development, platform focus, marketing, and revenue forecasting.

🛠️ Key Operations & Commands Executed

Below are the core operations implemented using Python, Pandas, Matplotlib, and Seaborn.

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

Many publishers focus heavily on specific platforms (e.g., PlayStation, Xbox). This reveals their investment behavior and loyal user communities.

📌 Publisher Dominance

One or two publishers have significantly higher game counts, showing stronger market presence and consistent releases.

📌 Uneven Market Spread

Some publishers diversify across multiple platforms, while others concentrate their releases on only a few — indicating varied business strategies.

📌 Platform Popularity Trends

Older platforms still show strong activity, suggesting:

High legacy value

Loyal gamers

Continued profitability for certain genres

📌 Growth Opportunities

Publishers with low presence on rising platforms have potential for expansion and revenue growth.

📈 Business Impact of the Findings
✔ Strategic Planning

Insights help decide which platforms should be prioritized for game releases.

✔ Marketing Optimization

Marketing teams can allocate budgets toward platforms with higher engagement.

✔ Revenue Forecasting

Platform-specific data assists in predicting:

Future sales

Market growth or decline

Investment efficiency

✔ Market Expansion

Publishers active on few platforms can expand to trending platforms (PC, PS5, Switch) to increase visibility and user base.

✔ Operational Efficiency

Retailers and distributors can better plan:

Inventory levels

Platform-specific stock

Regional supply strategies





