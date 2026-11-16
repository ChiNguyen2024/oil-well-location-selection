# Oil Well Location Selection

ML model and Bootstrap analysis to determine the optimal drilling region based on profit and risk assessment.

## Data
- **Source:** oil company internal data
- **Coverage:** three regions, 100,000 wells each
- **Features:** three geological features (f0, f1, f2), oil reserve volume (product, thousand barrels)

## Workflow
- Initial data analysis: oil reserve distribution by region, duplicate check
- Linear regression model for each region, quality evaluation (RMSE)
- Break-even volume calculation
- Bootstrap analysis (1,000 iterations): profit distribution, 95% confidence interval, loss risk estimation
- Final region selection based on loss risk < 2.5% criterion

## Key Findings

| Region | Avg Profit (k RUB) | 95% CI (k RUB) | Loss Risk | RMSE |
|--------|--------------------|--------------------|-----------|------|
| 1 | 405,254 | –81,207 – 920,424 | > 2.5% | 37.76 |
| 2 | **436,213** | **10,956 – 815,993** | **< 2.5%** | 0.89 |
| 3 | 371,650 | –155,335 – 875,847 | > 2.5% | 40.15 |

- **Region 2** — the only one with loss risk below the acceptable threshold (2.5%) and the highest average profit
- Regions 1 and 3 rejected due to negative confidence interval bounds
- Break-even volume — 111.11 thousand barrels; regional averages fall below this mark, confirming the need for model-based well selection

## Tech Stack
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-lightgrey)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-lightgrey)
![NumPy](https://img.shields.io/badge/NumPy-lightgrey)
![Matplotlib](https://img.shields.io/badge/Matplotlib-lightgrey)

## Repository Structure
```
├── oil_well_location_selection.ipynb  # main notebook
└── README.md
```
