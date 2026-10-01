# COVID-19 Deaths Across U.S. States (2020–2026)

**[Live dashboard on Tableau Public](https://public.tableau.com/app/profile/atharva.kurlekar/viz/COVID-19DeathsAcrossU_S_States2020-2026/Dashboard1)**

Interactive Tableau dashboard of CDC weekly mortality records. Trend, map, and heatmap views show how COVID-19's share of all deaths moved across 50 states, D.C., and Puerto Rico.

![Dashboard](dashboard.png)

## Question

How did COVID-19 mortality shift across U.S. states over six years, and which states were hit hardest relative to all deaths?

Comparing raw death counts favors large states. The main metric is **COVID share of total deaths**, so New Jersey can be compared with Texas on the same scale.

## Data

[CDC NCHS, Provisional COVID-19 Death Counts by Week Ending Date and State](https://data.cdc.gov/NCHS/Provisional-COVID-19-Death-Counts-by-Week-Ending-D/r8kw-7aab) (`data.cdc.gov`). Public-domain file in this repo: 23,760 rows, including **18,954 weekly records** across 50 states, D.C., Puerto Rico, New York City, and the national total. Vintage date: 24 Sep 2026.

## Cleaning

- Kept **weekly** rows only (`Group = By Week`) and dropped **United States** so the national total is not double-counted with states
- Merged **New York City into New York** (CDC publishes them as separate jurisdictions)
- Built **Year** from the week-ending date (CDC leaves some year values blank or as `2019/2020`)
- Calculated **COVID share of total deaths** = COVID-19 deaths / all-cause deaths
- Dropped the most recent 4 weeks for **death-certificate reporting lag**
- Result: **18,044** cleaned state-week rows, 52 jurisdictions, 4 Jan 2020–22 Aug 2026

## Findings

- Weekly COVID deaths **peaked at 26,091** in the week ending **9 Jan 2021**
- COVID's share of all deaths was **13.5% in 2021**, then **7.6% in 2022**, **2.3% in 2023**, and **0.5% in 2025**. The drop after 2022 appears in every state on the heatmap
- In 2020–21, the highest COVID shares were **New York (16.3%)**, **Texas (15.6%)**, and **New Jersey (15.4%)**. Texas and California had the most COVID deaths; New York and New Jersey were among the hardest hit relative to all deaths

## Tools

Tableau Public

## Repo

| File | What it is |
| --- | --- |
| [dashboard.png](dashboard.png) | Full dashboard screenshot |
| [Provisional_COVID-19_Death_Counts_by_Week_Ending_Date_and_State.csv](Provisional_COVID-19_Death_Counts_by_Week_Ending_Date_and_State.csv) | CDC source extract used in the workbook |
