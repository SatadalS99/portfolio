# Satadal Santra

**M.Sc. Data Science student at TU Dortmund** — open to Werkstudent and Praktikum roles in Data Science across NRW.

Eight years' prior experience with SAP/ERP master data and MIS reporting at a state power utility, now applied to forecasting, clustering and simulation on real industry datasets.

[LinkedIn](https://www.linkedin.com/in/satadals/) · satadals121@gmail.com · Bochum, Germany

---

## Skills

- **Languages:** Python, SQL
- **Libraries:** pandas, NumPy, scikit-learn, statsmodels, SciPy, Matplotlib, Seaborn, Plotly, Streamlit
- **Databases:** PostgreSQL, MySQL
- **Tools:** Jupyter, Git, Docker, VS Code, Anaconda, SAP
- **Methods:** time series forecasting, clustering & segmentation, anomaly detection, statistical inference, Monte Carlo simulation, hypothesis testing, cross-validation
- **Coursework:** Advanced Statistical Learning, Statistical Learning for Big Data, Applied Bayesian Data Analysis, Monte Carlo Simulation, Generalized Linear Models

---

## Projects

### 1. Weekly Demand Forecasting — Industry Case Study
*Team seminar project, Fakultät Statistik, TU Dortmund — Real World Solution Summit 2026*

Forecasting weekly parcel volumes for capacity planning at Customer × Product × calendar-week granularity, across 37 active customer–product lines over a 16-week horizon.

**My contribution — exploratory analysis and the customer-based modelling approach.**

- EDA established the modelling constraints: demand is highly skewed and concentrated in a small number of high-volume lines, with a mild structural decline over the observation period.
- Hypothesis testing showed the two product lines are statistically independent within a customer — robust across timescales and after multiple-testing correction — ruling out substitution effects and justifying line-by-line modelling.
- Built an individual time series per customer–product line and evaluated a pool of candidate models on each — naïve, seasonal, trend, Croston, ARIMA, Holt-Winters, machine learning and robust shrinkage.
- Model selection ran on a fixed training window under time-based validation with no look-ahead; each selected model was then validated on unseen test data before forecasting.
- **Outcome:** per-line model selection outperformed the best single global rule. No model won across the board — volatile and intermittent lines favoured robust and intermittent-demand methods, while stable lines favoured smooth ones.
- Designed for operational safety: the robust global rule is retained as an automatic fallback if a tailored model destabilises, and high-volatility lines are flagged so account teams can act early.

**Tech stack:** Python, pandas, statsmodels, scikit-learn

> Conducted under a university–industry partnership. Data, figures and code are not published.

---

### 2. New-Customer Drop-off Segmentation — Industry Case Study
*Team seminar project, Fakultät Statistik, TU Dortmund — Real World Solution Summit, SoSe 2026*

Brief covered customer clustering, basket co-purchase analysis and anomaly detection on an anonymised retail transaction extract.

**My contribution — new-customer drop-off patterns.**

- The problem: new customers joined and went quiet after one or two orders, but every drop-off received the same generic re-engagement email regardless of behaviour — no early warning, no way to prioritise.
- K-Means clustering (Euclidean) on a weekly-trajectory matrix: one row per new customer, one column per week of the observation window.
- Each row was **min–max normalised**, so clustering grouped by the *shape* of behaviour over time rather than by order volume. Without that step, segments separate on how much people buy — which the business already knows — instead of on how they disengage, which is the actionable signal.
- Candidate values of K compared against five criteria (Elbow, Silhouette, Davies–Bouldin, Calinski–Harabasz, minimum cluster size); the selected K won on four of the five.
- Segments projected onto the first two principal components to verify separation.
- **Outcome:** the clustering resolved a single declining average into distinct behavioural archetypes — never activated, gradually building, and peak-then-fade. Each has its own identifiable trigger week and its own appropriate response, replacing the one-size-fits-all email and letting retention spend go where it can actually be recovered.

**Tech stack:** Python, pandas, scikit-learn, PCA

> Conducted under a university–industry partnership. Data, figures and code are not published.

---

### 3. Portfolio Optimization with Monte Carlo Simulation
*Final project, "On the Theory and Practice of Monte Carlo Simulations", TU Dortmund — WiSe 2025/26*

[Repository](https://github.com/SatadalS99/portfolio-mc-optimization)

A nine-phase simulation framework for building and stress-testing equity portfolios, using five years of daily data for seven US large-caps (2020–2024, 1,221 return observations, 80/20 chronological split). Independent work.

- **Simulation engine:** correlated multivariate scenarios via Box–Muller and Marsaglia-polar drivers with Cholesky factorisation, validated against historical moments before use.
- **Why simulation:** normality is rejected for all seven assets (Jarque–Bera; excess kurtosis up to 14.5) with volatility clustering across the panel, so variance alone is an incomplete risk measure and closed-form tail estimates are unreliable.
- **Scenario models compared:** multivariate normal, historical bootstrap, and a two-regime stress mixture. Tail behaviour proved strongly model-dependent — the plain MVN model is the least conservative at the 99% level.
- **Optimisation:** Markowitz mean–variance (SLSQP) benchmarked against Monte Carlo random search with common random numbers. The two agree on max-Sharpe allocations but diverge under a min-CVaR objective, which shifts weight toward defensive names.
- **Rigour:** convergence diagnostics confirming the 1/√N rate; variance reduction via antithetic variates, control variates and importance sampling (VRF ≈ 2.4–2.7 on 99% tail estimates); estimation risk quantified by bootstrap and Bayesian Gibbs sampling; out-of-sample validation with Kupiec and Christoffersen backtests.

**Tech stack:** Python, NumPy, pandas, SciPy, Matplotlib · Fully reproducible (fixed seed), MIT licensed

---

### 4. German Wholesale & Retail Trade Analysis (2005–2020)
[Repository](https://github.com/SatadalS99/Annual_statistics_of_wholesale_and_retail_trade_de) · [Notebook](https://github.com/SatadalS99/Annual_statistics_of_wholesale_and_retail_trade_de/blob/main/src/Economic_Activity_Analysis.ipynb)

Fifteen years of German wholesale and retail trade statistics analysed end to end, from raw ingestion through to structural findings: average sector profitability of 28.69%, a productivity gap of €268 per person (large firms) versus €116 (micro firms), and 27% net market growth since 2005 with investment intensity rising +0.026%/year.

**Tech stack:** Python, pandas, NumPy, Matplotlib, Seaborn, openpyxl

---

### 5. Gold Price Prediction
[Repository](https://github.com/SatadalS99/Gold_price_prediction) · [Notebook](https://github.com/SatadalS99/Gold_price_prediction/blob/main/Gold_price_prediction_using_decison_trees.ipynb) · [Streamlit app](https://gold-price-prediction-satadal.streamlit.app/)

End-to-end regression pipeline predicting gold prices from market and economic indicators. Benchmarked a Random Forest Regressor against Gradient Boosting, reaching **R² = 0.814** on the held-out set. Feature analysis identified Silver (SLV) as the strongest single predictor (r = 0.87).

**Tech stack:** Python, pandas, NumPy, scikit-learn, Matplotlib, Streamlit

---

### 6. Healthcare Accessibility in Sudan — Omdena Sudan Chapter
*Volunteer collaborator, Feb–Mar 2024*

[Repository](https://github.com/OmdenaAI/SudanChapter_AnalyzeHealthcareAccessibility)

Open-source challenge building a machine learning system to forecast disease outbreaks and map healthcare facility accessibility in Sudan, where healthcare access is severely constrained by conflict and displacement.

- Data collection and preprocessing of historical and geospatial health datasets — resolving missing values, reconciling inconsistent sources, and building the cleaned feature sets used downstream.
- Exploratory analysis identifying high-risk disease trends and regional access barriers.
- The team's logistic regression models were trained on these feature sets and deployed as an interactive web application.
- Worked asynchronously with a distributed international team via Git/GitHub.

**Tech stack:** Python, pandas, NumPy, scikit-learn, Matplotlib

---

## Education

- **M.Sc. Data Science**, TU Dortmund University — 2021–2027 (expected)
- **Master of Computer Applications (MCA)**, West Bengal University of Technology — 2012
- **Bachelor of Computer Applications (BCA)**, West Bengal University of Technology — 2009

## Certifications

- [AI Engineer Core Track: LLM Engineering, RAG, QLoRA, Agents](https://www.udemy.com/certificate/UC-fa433f70-7544-4ef6-94eb-4af44aa4e370/) — Udemy
- [AWS Certified Machine Learning Specialty 2025 – Hands On!](https://www.udemy.com/certificate/UC-84826733-80a1-4a86-8175-bae4b63b3480/) — Udemy
- [SQL & Database Design A-Z: MS SQL Server + PostgreSQL](https://www.udemy.com/certificate/UC-8e25770a-2c19-4d31-bd32-3bab1523ebcd/) — Udemy

## Professional Experience

- **Office Executive**, WBSEDCL (state power utility), India — 2013–2021
  SAP/ERP master data management, MIS reporting, billing and revenue analysis
- **Online Mathematics Tutor**, 1to1 Tutor, India — 2010–2013

## Languages

English C1 · German B1 · Bengali, Hindi (native/fluent)
