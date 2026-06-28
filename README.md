

Descriptive statistics and hypothesis testing applied to a 3,000-order supply chain dataset, validating supplier performance, regional cost gaps, and demand patterns with rigorous statistical methods.


Project Overview

This is TDI Python Data Analysis Programme. The goal was to go beyond exploratory analysis and use formal hypothesis testing to confirm — or reject — patterns found in the data.

6 hypotheses were tested. 4 were confirmed significant. The findings include a statistically proven supplier performance gap, a large regional cost difference, and the surprising finding that demand is stable year-round despite visible month-to-month variation.

Programme: TDI Python Data Analysis 

Dataset: Supply Chain Dataset — 3,000 orders, 5 suppliers, 5 regions

Analyst: Ogo Chukwuemeka Okereke


Hypotheses Tested

#HypothesisTest UsedResultH1Supplier A has a better on-time rate than Supplier EChi-Square✅ Reject H₀H2Order quantity correlates with total costPearson Correlation✅ Reject H₀H3Lead time variability predicts late deliveriesPearson Correlation❌ Fail to reject (n=5)H4Demand is significantly seasonalOne-Way ANOVA❌ Fail to rejectH5Lead time strongly predicts actual delivery timePearson Correlation✅ Reject H₀H6Regional cost differences are statistically significantOne-Way ANOVA✅ Reject H₀


Key Findings

H1 — Supplier Performance (Chi-Square)


Supplier A on-time rate: 94.3% [95% CI: 92.6% – 95.9%]
Supplier E on-time rate: 76.0% [95% CI: 72.8% – 79.3%]
χ²(1) = 95.23, p < 0.001, Cramér's V = 0.341 (Medium effect)
The 18.3 percentage point gap is statistically real — not random chance


H2 — Quantity vs Cost (Pearson Correlation)


r = 0.70, p < 0.001 — strong positive correlation
Quantity explains 49% of total cost variation
Regression: Cost = base + $X × Quantity (reliable for budgeting)


H3 — Lead Time Variability (Pearson Correlation)


r = -0.730, but p = 0.161 — not significant
Reason: only 5 supplier groups, too small for statistical power
The negative trend is real; more data is needed to confirm it


H4 — Demand Seasonality (ANOVA)


F = 1.41, p = 0.161 — fail to reject H₀
Month-to-month variation exists but is random noise, not a seasonal pattern
Demand is statistically stable throughout the year


H5 — Lead Time vs Delivery Time (Pearson Correlation)


r = 0.92, p < 0.001 — very strong positive correlation
Planned lead time explains 85% of actual delivery time variance
Negotiating shorter lead times is the single most effective way to cut delivery time


H6 — Regional Costs (One-Way ANOVA)


F = 108.8, p < 0.001, Eta-squared = 0.127 (Large effect)
USA average: $91.9K | Mexico average: $7.4K — a $84.5K per-order gap
Region explains 12.7% of total cost variation



Statistical Methods Used

MethodUsed ForChi-Square TestComparing categorical outcomes between two suppliersOne-Way ANOVAComparing a numeric variable across 3+ groupsPearson CorrelationMeasuring linear relationships between numeric variablesLinear RegressionQuantifying the cost impact of quantity changesCramér's VEffect size for chi-square testsEta-squared (η²)Effect size for ANOVA95% Confidence IntervalsShowing the precision of proportion estimatesBonferroni CorrectionAdjusting for multiple comparison riskMann-Whitney UNon-parametric alternative to t-testKruskal-WallisNon-parametric alternative to ANOVAStatistical Power AnalysisChecking if sample sizes are large enough to detect effects


Extra Challenges

Challenge 1 — Bonferroni Correction

Running 6 tests raises the risk of a false positive. After applying the corrected threshold (α = 0.05 ÷ 6 = 0.0083), all 4 significant findings remained significant. The conclusions are robust to multiple comparison concerns.

Challenge 2 — Non-Parametric Tests

Cost data is right-skewed, which violates ANOVA's normality assumption. Mann-Whitney U and Kruskal-Wallis were run as alternatives — both confirmed the same conclusions as the parametric tests. The findings hold regardless of distributional assumptions.

Challenge 3 — Statistical Power Analysis

The chi-square test for H1 was analysed for power. With n = 1,202 total observations and Cramér's V = 0.341, estimated power = 99.9%. The minimum required sample for 80% power was approximately 85 total observations. Our actual sample was over 14× that minimum.


Business Recommendations


Issue a formal performance improvement plan to Supplier E immediately. The 76% on-time rate is statistically, significantly worse than every other supplier — this is a proven business risk, not noise.
Route cost-sensitive orders to Mexico or China. The $84.5K cost gap vs USA suppliers is statistically large (η² = 0.127). For quality-critical or time-sensitive orders, USA suppliers justify the premium.
Use quantity as a cost predictor in budgeting. With r = 0.70 and 49% variance explained, order quantity is a reliable and statistically validated input for procurement cost forecasting.
Negotiate shorter lead time agreements. Lead time explains 85% of actual delivery time (r = 0.92, p < 0.001). This is the single strongest lever for improving delivery speed.
Do not adjust inventory for seasonality. Demand is statistically stable year-round (ANOVA p = 0.161). Month-to-month swings are random — building seasonal stock adjustments around them wastes resources.



Project Structure

supply-chain-week-12/
│
├── supply_chain_week_12_project.ipynb   # Main analysis notebook
├── python_supply_chain_dataset.csv      # Source dataset (3,000 orders)
│
├── visuals/
│   ├── w12_t1_supplier_comparison.png   # H1: Chi-square results
│   ├── w12_t2_regional_anova.png        # H6: Regional ANOVA
│   ├── w12_t3_correlations.png          # H2 & H3: Scatter plots
│   ├── w12_t4_seasonality.png           # H4: Monthly demand
│   └── w12_summary_dashboard.png        # Full results dashboard
│
└── README.md


How to Run

bash# Clone the repo
git clone https://github.com/your-username/supply-chain-week-12.git
cd supply-chain-week-12

# Install dependencies
pip install pandas numpy matplotlib seaborn scipy

# Open the notebook
jupyter notebook supply_chain_week_12_project.ipynb


Run cells in order starting from Cell 1. Each cell is labelled and self-contained with explanations of why each test was chosen.




Validation of Week 11 EDA Findings

EDA ClaimOutcomeSupplier A is the most reliable supplier✅ Validated — Chi-Square p < 0.001Supplier E is the least reliable✅ Validated — 18.3% gap confirmed realRegional costs vary significantly✅ Validated — ANOVA F = 108.8, p < 0.001Demand shows a seasonal Q4 slowdown❌ Not validated — ANOVA p = 0.161Quantity is a strong predictor of cost✅ Validated — Pearson r = 0.70, p < 0.001


Tools & Technologies


Python 3 — analysis and testing
Pandas & NumPy — data preparation and calculations
SciPy — statistical tests (chi-square, ANOVA, Pearson, Mann-Whitney, Kruskal-Wallis, power analysis)
Matplotlib & Seaborn — visualisations
Jupyter Notebook — development environment (VS Code)



Author

Ogo Chukwuemeka Okereke

Data Analyst · Abuja, Nigeria

LinkedIn · Portfolio

