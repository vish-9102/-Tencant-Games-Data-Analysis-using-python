# -Tencant-Games-Data-Analysis-using-python

Game Sales Analytics Project
A Data-Driven Exploration Using Python, Pandas, Matplotlib & Seaborn
1. Project Overview

This project focuses on analyzing video game sales data to understand how the Top 5 Publishers perform across various gaming platforms.
Using Python’s data analytics and visualization libraries, the project uncovers trends, patterns, and relationships that highlight platform dominance, publisher strengths, and potential areas for market expansion.

The goal is to convert raw sales data into clear insights that can support business decisions related to product strategy, platform focus, marketing, and budgeting.

2. Key Operations & Commands Executed

Below are the core operations performed using Python, Pandas, Matplotlib, and Seaborn.

*Data Loading & Cleaning
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("games.csv")
df.dropna(inplace=True)

*Filtering Top 5 Publishers
top_publishers = df["Publisher"].value_counts().head(5).index
top_5_data = df[df["Publisher"].isin(top_publishers)]

*Countplot: Publisher vs Platform
sns.countplot(data=top_5_data, x="Publisher", hue="Platform")
plt.xticks(rotation=45)
plt.show()

*Crosstab: Publisher vs Platform
df_stacked_plot = pd.crosstab(
    index=top_5_data["Publisher"],
    columns=top_5_data["Platform"]
)
print(df_stacked_plot)

*Stacked Bar Chart
df_stacked_plot.plot(kind="bar", stacked=True, figsize=(10,6))
plt.xticks(rotation=45)
plt.show()

*Statistical Summaries
top_5_data.describe(include="all")


These operations form the backbone of the analysis, enabling both data transformation and visual story-telling.

*3. Vital Insights Gathered From the Analysis
 1. Platform Concentration

Some publishers focus heavily on specific platforms (e.g., PlayStation or Xbox), revealing their long-term investment and user base strength.

 2. Publisher Dominance

One or two publishers clearly lead in game volume, showing greater market influence and more frequent game releases.

 3. Uneven Market Spread

Certain publishers diversify across many platforms, while others concentrate on only 2–3, indicating different business strategies.

 4. Platform Popularity Trends

Older platforms still show significant game counts, suggesting:

High legacy value

Strong player loyalty

Long-term profitability for certain genres

 5. Potential Growth Opportunities

Low platform presence for some publishers highlights untapped markets where expansion can create new revenue streams.

4. Business Impact of the Findings
 Strategic Planning

Publishers can choose which platforms deserve priority when launching future titles.

 Marketing Optimization

Marketing budgets can be allocated toward platforms with higher game volume and user engagement.

 Revenue & Forecasting

Understanding which platforms generate more games helps predict:

Future sales potential

Platform growth or decline

Investment value

 Market Expansion Opportunities

Publishers with low activity on growing platforms (like modern consoles or PC) can:

Expand their audience

Boost revenue

Increase brand visibility

 Operational Efficiency

Retailers and distributors can optimize:

Inventory management

Regional platform-specific supply strategies
