# Marketing-A/B-Testing-Analysis

## Overview
Marketing companies strive to run successful campaigns, but the complexity of the market means that several strategies may be effective. To determine the best approach, companies often conduct A/B tests, which are randomized experiments comparing two or more variations of a variable (e.g., webpage, page element, banner). This allows companies to identify which version has the highest impact on business metrics.

This dataset is designed to analyze the performance of advertisements in an A/B test setting and answer the following key questions:
1. Would the campaign be successful?
2. If the campaign was successful, how much of that success could be attributed to the ads?

## Experiment Design
In this A/B test:
- The **experimental group** is exposed to advertisements.
- The **control group** is exposed to a public service announcement (PSA) or nothing, in the same format and placement as the advertisements.

By comparing these groups, we can evaluate ad effectiveness, estimate the revenue impact, and determine if differences are statistically significant.

## Dataset Information

### Data Source
The dataset includes user interaction data from an A/B test conducted for a marketing campaign.

### Data Dictionary
| Column Name   | Description |
|--------------|-------------|
| `index`       | Row index |
| `user id`     | Unique identifier for each user |
| `test group`  | Indicates whether the user was in the **ad** group (saw advertisements) or **psa** group (saw public service announcements) |
| `converted`   | Boolean value indicating whether the user made a purchase (True) or not (False) |
| `total ads`   | Number of ads viewed by the user |
| `most ads day` | Day of the week when the user saw the highest number of ads |
| `most ads hour` | Hour of the day when the user saw the highest number of ads |

## Data Analysis Process

### 1. Data Preprocessing
- Removing duplicate entries based on `user id`.
- Dropping unnecessary columns such as `index` and `user id`.
- Ensuring categorical variables have the correct number of unique values.

### 2. Exploratory Data Analysis (EDA)
- **Univariate Analysis:**
  - Count plots and pie charts for categorical variables (`test group`, `converted`, `most ads day`, `most ads hour`).
  - Histograms and boxplots for numerical variables (`total ads`).
- **Bivariate Analysis:**
  - Conversion rates across different test groups.
  - Conversion trends based on `most ads day` and `most ads hour`.
  - Relationship between `total ads` and `converted`.

### 3. Statistical Testing
- **Chi-Square Test:** Used to determine if conversion rates differ significantly between the ad and PSA groups.
- **T-Tests & Other Significance Tests:** Evaluate whether the observed differences in conversions are statistically meaningful.

## Key Metrics to Evaluate
- **Conversion Rate**: The proportion of users who made a purchase in each test group.
- **Lift**: The percentage increase in conversion rate due to the ad exposure.
- **Statistical Significance**: Whether the observed differences are due to chance or an actual effect of the ads.

## Conclusion
The analysis of this dataset allows for a data-driven approach to assessing marketing campaign effectiveness. By running A/B tests, companies can make informed decisions on ad performance, campaign impact, and future investment in digital advertising strategies.

