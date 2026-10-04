1. Customer churn prediction — Telecom

- _Business problem:_ acquiring customers costs 5–25x retaining them; predict who's about to leave so retention offers target the right people.
- _Dataset:_ IBM Telco Customer Churn (public, ~7k rows) — needs real cleaning: categorical encoding, class imbalance (~27% churn), feature engineering on tenure/charges.
- _Rubric fit:_ perfect for methodology defense — compare logistic regression (interpretable baseline) vs. random forest vs. gradient boosting vs. a small neural net on precision/recall tradeoffs. Defense angle: "we optimize recall because missing a churner costs more than a wasted retention offer."

2. Loan default prediction — Fintech/Lending

- _Business problem:_ approve profitable loans while controlling default risk.
- _Dataset:_ LendingClub loan data (public, hundreds of thousands of rows) — messy real-world data: missing values, outliers, high-cardinality categoricals.
- _Rubric fit:_ compare logistic regression vs. trees vs. neural nets; strong defense material on interpretability vs. accuracy (regulators require explainable decisions — a great talking point in your final defense) and ROC-AUC vs. profit-based thresholding.

1. Happiness Studies
	1. https://arxiv.org/abs/2206.00574