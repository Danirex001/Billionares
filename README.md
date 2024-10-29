# Table of content
- [Billionaires Wealth Analysis Overview](#billionaires-wealth-analysis-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaningpreparation)
- [Dataset Columns](#dataset-columns)
- [Objectives](#objectives)
- [Analysis](#analysis)
- [Findings](#findings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)

# Billionaires wealth Analysis Overview

This repository contains an analysis of a Billionaires wealth dataset, including information such as individuals' net worth, industries, and country-specific economic indicators.

## Data source

**File**: `Billionaires Statistics Dataset - Billionaires Statistics Dataset`

### Tools
- Excel - Data Cleaning [Download here](http://microsoft.com)
- Python - Data Analysis and Visualization

#### Data Cleaning/Preparation

In the initial data preparation phase, I performed the following tasks:
1.  Data loading and inspection
2.  Handling missing values
3.  Data cleaning and formatting


The dataset includes the following columns:
- **rank**: Ranking of wealthiest individuals
- **finalWorth**: Net worth of individuals in USD
- **category**: Industry category
- **personName**: Full name of the individual
- **age**: Age of the individual
- **country**: Country of residence
- **city**: City of residence
- **source**: Source of wealth
- **industries**: Main industry of wealth
- **selfMade**: Whether self-made or inherited
- ... *(and other columns)*

### Objectives
1. Identify the top industries by billionaire count.
2. Self-Made vs Inherited Wealth.
3. Demographic Distribution Analysis

## Analysis
   ```python
# Code snippet to analyze top industries by billionaire count
plt.figure(figsize=(10, 6))
plt.bar(rut['industries'], rut['personName'], color='skyblue')
plt.xlabel('Industry')
plt.ylabel('Number of Billionaires')
plt.title('Top 10 Industries with Most Billionaires')
plt.xticks(rotation=45, ha='right')  # Rotate x-axis labels for readability
plt.tight_layout()  # Adjust layout to prevent label cutoff
plt.savefig('bar_chart.png')
plt.show
```
![download](https://github.com/user-attachments/assets/7c579008-3a5f-48bf-8d25-501d64dc148d)

 ```python
# Group by 'selfMade' to see how many are self-made vs inherited
self_made_count = df.groupby('selfMade')['personName'].count().reset_index()

# Rename columns for clarity
self_made_count.columns = ['self_made', 'count']

# Display the result
print(self_made_count)
```
 False    166 ,    True    309

 ```python
   # Plot the age distribution to understand the spread of ages
import matplotlib.pyplot as plt

# Histogram for the age distribution
df['age'].plot(kind='hist', bins=20, title="Age Distribution of Billionaires")
plt.xlabel('Age')
plt.show()
```
![download](https://github.com/user-attachments/assets/767a3375-8adf-4a49-9d6e-3457c9efab74)

---

### Findings
- **Top Industries**: The majority of billionaires are concentrated in specific industries such as technology, finance, and retail. Technology, in particular, has the highest number of billionaires, followed closely by finance.
- **Self-Made vs. Inherited Wealth**: There is a higher proportion of self-made billionaires than those with inherited wealth, indicating the significant role of entrepreneurship.
- **Age Distribution**: The age distribution of billionaires shows a concentration in the 50-70 age range, with fewer younger and older billionaires.
- **Country-Level Insights**: Countries with higher GDPs, like the United States and China, have a larger concentration of billionaires. Additionally, countries with high life expectancy tend to have a higher number of billionaires, potentially due to better health and economic conditions.

### Recommendations
1. **Foster Innovation and Entrepreneurship**: Policymakers could encourage economic growth by fostering environments conducive to entrepreneurship, especially in technology and finance.
2. **Economic Diversification**: Nations seeking higher concentrations of wealth creation could diversify their economies to include high-growth sectors like technology.
3. **Education and Health Investments**: Countries could improve their economic resilience by investing in education and health, which could indirectly support wealth creation.
4. **Support for Self-Made Initiatives**: Governments might consider supporting self-made ventures through favorable policies, as self-made wealth is significant in the billionaire demographic.

### Limitations
- **Data Completeness**: The dataset may not cover all billionaires globally, potentially skewing results towards certain countries with better data coverage.
- **Currency and Economic Variations**: Net worth data may be impacted by currency fluctuations and does not adjust for purchasing power parity across countries.
- **Time Constraints**: Analysis was conducted within a limited timeframe, which may restrict deeper analysis into demographic correlations.
- **Static Snapshot**: The dataset represents a single point in time, not accounting for changes in billionaire net worth or demographics over time.

---


