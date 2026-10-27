# Emotional Tone and Fundraising Success: A Text Analytics Study of GoFundMe Campaigns

### Python | Natural Language Processing | SEANCE | GALC | EmoLex | Statistical Regression

## Project Overview

This project examines the relationship between emotional language and fundraising success in GoFundMe campaigns.

I analyzed **1,231 GoFundMe campaign descriptions** to understand whether emotions expressed in fundraising stories are associated with the amount of money raised and the number of donors.

I used dictionary-based text analysis to measure emotional language. I then used Python and statistical regression to examine its relationship with fundraising outcomes.

An important part of this project was comparing two emotion dictionaries, GALC and EmoLex, to determine whether different approaches to measuring emotions produced similar findings.

## Research Questions

This project addresses two main research questions.

**RQ1:** Is emotional language in GoFundMe campaign descriptions associated with the percentage of fundraising goals achieved?

**RQ2:** Is emotional language associated with the number of donors supporting a campaign?

I also examined whether the results changed when emotional language was measured using different dictionaries.

## Dataset

The original dataset contained 1,242 GoFundMe campaigns.

After checking missing values, cleaning numerical information, and removing unusable records, I retained **1,231 campaigns** for text analysis.

The dataset included campaign descriptions, fundraising goals, amounts raised, donor counts, Facebook shares, GoFundMe hearts, and fundraising duration.

The regression samples were smaller because of missing predictor values and additional data-cleaning rules.

## Research Methodology

### 1. Data Cleaning and Preprocessing

I used Python and Pandas to clean the original dataset.

I corrected numerical values, checked missing observations, calculated fundraising duration in days, and prepared the campaign descriptions for text analysis.

I also calculated the percentage of fundraising goals achieved.

### 2. Dictionary-Based Text Analysis

I used **SEANCE (Sentiment Analysis and Cognition Engine)** to measure emotional language.

Two dictionaries were examined.

**GALC (Geneva Affect Label Coder)**

I selected four emotional constructs:

Love, Gratitude, Hope, and Anger.

These constructs represent emotional themes that may be relevant to charitable giving.

**EmoLex (NRC Emotion Lexicon)**

I conducted an additional analysis using four constructs:

Trust, Anticipation, Sadness, and Fear.

These emotions may communicate confidence, future expectations, hardship, and urgency.

I compared the two dictionaries to examine whether the findings remained consistent across different emotional measures.

### 3. Statistical Regression

I developed two regression models.

**Model A:** Percentage of fundraising goal achieved.

**Model B:** Number of donors.

The models included four emotional constructs, GoFundMe hearts, Facebook shares, and fundraising duration.

I estimated the models using ordinary least squares (OLS) regression with **HC3 robust standard errors**.

### 4. Sensitivity Analysis

I conducted additional analyses to examine the stability of the findings.

For Model A, I excluded the highest 1% of fundraising percentages to investigate the influence of extreme observations.

For Model B, I removed GoFundMe hearts because this variable was almost perfectly correlated with donor counts.

## Key Findings

### Emotional Language and Fundraising Success

Neither GALC nor EmoLex identified statistically significant emotional predictors in the primary regression models at the 5% significance level.

Although EmoLex detected emotional language in more campaign descriptions than several selected GALC categories, this broader coverage did not produce significant emotional coefficients.

### Fundraising Duration

Fundraising duration showed a statistically significant negative association with the percentage of fundraising goals achieved.

This relationship appeared in both GALC and EmoLex models. However, the estimated coefficient became smaller after excluding extreme fundraising outcomes.

### GoFundMe Hearts and Donor Counts

GoFundMe hearts and donor counts were almost perfectly correlated.

This contributed to an unusually high R² of approximately 0.997 in the primary donor-count models.

After removing GoFundMe hearts, the models explained approximately 56% of donor-count variation.

### Facebook Shares

Facebook shares showed a positive and statistically significant association with donor counts in both sensitivity models that excluded GoFundMe hearts.

These findings describe statistical associations rather than causal relationships.

## Regression Model Comparison

| Model                        | Dictionary | Observations |     R² |
| ---------------------------- | ---------- | -----------: | -----: |
| Percent Raised               | GALC       |        1,181 | 0.0293 |
| Percent Raised               | EmoLex     |        1,181 | 0.0247 |
| Number of Donors             | GALC       |        1,192 | 0.9973 |
| Number of Donors             | EmoLex     |        1,192 | 0.9973 |
| Percent Raised — Sensitivity | GALC       |        1,169 | 0.0163 |
| Percent Raised — Sensitivity | EmoLex     |        1,169 | 0.0094 |
| Donors Without Hearts        | GALC       |        1,192 | 0.5616 |
| Donors Without Hearts        | EmoLex     |        1,192 | 0.5642 |

## Technologies and Tools

**Programming:** Python

**Data Processing:** Pandas, NumPy

**Text Analytics:** SEANCE, GALC, NRC EmoLex

**Statistical Analysis:** Statsmodels, OLS Regression, HC3 Robust Standard Errors

**Development Environment:** Google Colab

**Version Control:** Git and GitHub

## Project Files

The repository contains the following materials.

**[Python Analysis Notebook](notebooks/GoFundMe_Emotion_Analysis_GitHub_Ready.ipynb)**

Contains data preprocessing, emotion scoring integration, regression analysis, sensitivity checks, and dictionary comparisons.

**[Final Research Report](report/)**

Presents the methodology, statistical results, interpretation, and limitations.

**[Statistical Tables](results/tables/)**

Contains descriptive statistics, regression results, and sensitivity analyses in CSV and PNG formats.

## Limitations

This study has several limitations.

Campaign descriptions were relatively short, which may have limited the measurement of emotional language.

Dictionary-based methods identify words associated with emotions, but they cannot fully understand context, sarcasm, or the feelings experienced by readers.

The fundraising outcomes were also highly skewed. Some campaigns raised much more money than their original goals.

The analysis was observational. Therefore, the results cannot establish causal relationships between emotional language and fundraising success.

## Data Availability and Reproducibility

The raw campaign descriptions and identifiable campaign information are not included in this public repository because they may contain sensitive personal stories and have reuse restrictions.

The notebook documents the analytical workflow. Reproducing the full analysis requires access to the source dataset and the corresponding SEANCE outputs.

The published tables provide aggregate results without exposing individual campaign descriptions.

## Project Context

This project was completed as part of graduate coursework in text analytics and statistical research.

It demonstrates practical experience in data preparation, natural language processing, dictionary-based construct measurement, regression modeling, sensitivity analysis, and interpretation of research findings.
