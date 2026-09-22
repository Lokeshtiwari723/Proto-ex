# Ranking Signal Analysis — Reviewer Decision Support

## What this project does
This project explores which observable search and content signals can help a reviewer decide which pages should be reviewed first for possible search-performance issues.

The output is a priority list for human review, not an automatic final verdict.

## Research question
**Which observable search and content signals can help us rank pages that should be reviewed first?**

## Features
- `gsc_impressions`
- `gsc_clicks`
- `gsc_avg_position`
- `word_count`
- `content_age_days`

The proxy target `is_declining_proxy` was built from `trend_direction`. `trend_direction` was excluded from the model features to avoid using the target-building signal as a feature.

## Validation and results
The model used a grouped train/test split by client:
- Total: 86,560
- Train: 75,670
- Test: 10,890
- Train clients: 29
- Test clients: 8
- Client overlap: 0

Recorded ranking results:
- Week-4 baseline Precision@50: **0.76**
- Logistic Regression Precision@50: **1.00**

These results are from the tested split and are not a claim of production performance.

## How to use the result
The ranking answers: **Which pages should a human reviewer look at first?**

It does not answer: **Which pages definitely have a problem?**

Human review remains necessary before taking action.

## Simple architecture
```text
Search/content data
→ Feature preparation
→ Proxy target construction
→ Grouped train/test split
→ Ranking model
→ Priority-ranked pages
→ Human reviewer
→ Review / decision
```

## Tools
The project was developed in a notebook workflow using Python packages including pandas, scikit-learn, matplotlib, duckdb, and huggingface_hub.

## Limitations
- The target is a proxy label, not a direct business outcome.
- The reported Precision@50 is from the tested validation setup.
- Many positive pages can remain outside the top 50.
- The model does not replace a human reviewer.
- No causal claim is made about the signals.

## Links
Live portfolio: https://lokesh-ai-ml-portfolio.netlify.app

Project paper: https://lokeshtiwari723.github.io/Proto-ex/paper/

## Transparency
AI assistance was used during planning and documentation. Reported results are based on the project work and notebook outputs that were checked.
