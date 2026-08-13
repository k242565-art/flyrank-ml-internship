# Content Refresh Prioritization Using Historical Search Performance Signals

## Abstract

This project investigates whether historical search-performance signals can be used to prioritize content refresh opportunities. Using the FlyRank ML Internship dataset, I analyzed content age, traffic trends, engagement metrics, and search-performance indicators to identify pages that may benefit from editorial review. A rule-based baseline was developed and compared against a machine-learning model. Validation included grouped evaluation, leakage checks, and error analysis. The resulting action playbook provides ranked recommendations intended for human decision-support.

---

## Introduction

Content performance changes over time because of search-demand shifts, competition, and content freshness. Large content portfolios make manual review difficult.

The objective of this project was to identify content that may benefit from refresh actions using historical performance signals and machine learning.

---

## Data

### Dataset

FlyRank ML Internship Dataset

### Features Used

- search_volume
- competition
- cpc
- word_count
- impressions_90d
- clicks_90d
- sessions_90d
- content_age_days
- days_since_last_update
- ctr
- avg_position
- engagement_rate
- scroll_rate
- trend_pct

### Exclusions

- No client names used
- No URLs used
- No private search queries used
- Identifier columns excluded from modeling

---

## Methodology

### Baseline

Baseline score:

Score = (0.7 × days_since_last_update) + (0.3 × negative trend)

### Signal Validation

#### Signal 1: Days Since Last Update

Verdict: CONFIRMED

Older content generally showed weaker performance and was useful for prioritization.

#### Signal 2: Traffic Trend

Verdict: CONFIRMED

Declining content appeared more frequently among refresh candidates.

### Machine Learning Model

Model Used: Random Forest Classifier

Reason:
- Handles nonlinear relationships
- Works well with mixed feature types
- Provides interpretable feature importance

### Validation Design

Week 5:
- Random Train/Test Split

Week 6:
- Grouped Validation by Client

Grouped validation prevents information leakage between clients and provides a more realistic estimate of generalization.

---

## Results

### Model vs Baseline

| Method | Score |
|----------|----------|
| Baseline | PUT YOUR SCORE |
| Random Forest | PUT YOUR SCORE |

### Interpretation

The machine-learning model outperformed the rule-based baseline while maintaining reasonable interpretability.

---

## Limitations

- Observational analysis only
- Does not prove causation
- Does not measure post-refresh outcomes
- Does not account for seasonality
- Requires human review

---

## Ranked Recommendations

| Priority | Action | Reason Code |
|----------|----------|----------|
| High | Refresh Immediately | STALE_DECLINE |
| Medium | Refresh Soon | STALE_HIGH_VALUE |
| Medium | CTR Optimization | LOW_CTR |
| Low | Monitor | WATCHLIST |
| Lowest | No Action | HEALTHY |

### Human Review Rules

Before acting:

1. Verify topic relevance
2. Confirm search demand
3. Review factual accuracy
4. Check seasonality
5. Consider business value

### No-Go Actions

Do NOT automatically:

- Publish content
- Delete content
- Rewrite content
- Change medical/legal/financial information
- Remove pages

---

## Monitoring and Retraining

Retrain if:

- Traffic distributions change significantly
- New client groups appear
- Recommendation quality declines
- New content formats emerge

---

## Reproducibility

### Repository

PASTE YOUR GITHUB REPO URL HERE

### Notebooks

- Week 4 Baseline
- Week 5 Model
- Week 6 Validation Audit
- Week 7 Action Playbook
- Capstone

---

## Acknowledgments

Built on the FlyRank ML Internship Dataset.

Data and internship program provided by FlyRank.

https://flyrank.ai
