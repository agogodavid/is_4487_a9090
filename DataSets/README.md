| **Discipline / Domain**                     | **Dataset**                                   | **Typical Analytics Use Cases**                  | **Used in...**        |
| ------------------------------------------- | --------------------------------------------- | ------------------------------------------------ |-----------------------
| **Finance & Banking**                       | `BankChurners.csv`                            | Customer churn, retention modeling, segmentation |                     |
|                                             | `bank_subscription.csv`                       | Campaign response, classification                |                     |
|                                             | `fintrust_loans.csv`                          | Credit risk, default prediction                  |                     |
|                                             | `adviseinvest_historical_data.csv`            | Portfolio analysis, time series                  |                     |
|                                             | `adviseinvest_new_customer_data.csv`          | Customer profiling, onboarding analytics         |                     |
|                                             | `aapl_stock_prices.csv`                       | Financial forecasting, trend analysis            |                     |
| **Marketing & Customer Analytics**          | `amazon 2.csv`                                | Purchase behavior, descriptive analytics         |                     |
|                                             | `amazon-reviews2.csv`                         | Sentiment analysis, text classification          |                     |
|                                             | `ecommerce_customer_orders.csv`               | Funnel analysis, RFM metrics                     |                     |
|                                             | `ecommerce_customer_reviews.csv`              | NLP, customer feedback mining                    |                     |
|                                             | `onlinefoods.csv`                             | Consumer preferences, classification             |                     |
|                                             | `airbnb_listings.csv`                         | Pricing strategy, feature importance             |                     |
|                                             | `spotify-classification.csv`                  | Recommendation systems, classification           |                     |
|                                             | `youtube.csv`                                 | Engagement analytics, content performance        |                     |
| **Human Resources & People Analytics**      | `merged_hr_data.csv`                          | Attrition prediction, workforce analytics        |                     |
|                                             | `megatelco_leave_survey_data_cleaning_v2.csv` | Survey analysis, sentiment, cleaning             |                     |
| **Operations & Supply Chain**               | `superstore_retail_orders.csv`                | Demand forecasting, operational KPIs             |                     |
|                                             | `streamflow_customer_churn.csv`               | Service usage, churn modeling                    |                     |
|                                             | `megatelco_historical_data.csv`               | Capacity planning, operational trends            |                     |
|                                             | `megatelco_new_customer_data.csv`             | Customer acquisition analytics                   |                     |
| **Hospitality & Service Management**        | `hotels.csv`                                  | Occupancy modeling, pricing analytics            |                     |
|                                             | `Restaurant_Reviews.tsv`                      | Service quality, sentiment analysis              |                     |
| **Media, Entertainment & Sports**           | `movie_reviews.tsv`                           | Text classification, sentiment                   |                     |
|                                             | `x_superbowl.csv`                             | Social media analytics, event impact             |                     |
| **Public Sector & Environmental Analytics** | `air_quality_by_county.csv`                   | Environmental impact, spatial analysis           |                     |
| **Technology & Product Analytics**          | `detectors.csv`                               | Product performance, anomaly detection           |                     |





## High-Level Diagnosis

Your current dataset bank is **very strong** in:

* Marketing / Customer Analytics
* Finance (investments, churn, credit)
* IS / Tech / Product analytics
* Some Operations & HR

But several majors **don’t see their core decisions reflected**, even though analytics is central to them.

---

## Summary Table: Coverage Gaps

| **Major**               | **Current Coverage** | **Action Needed** |
| ----------------------- | -------------------- | ----------------- |
| Accounting              | ❌ None               | High priority     |
| Entrepreneurship        | ⚠️ Indirect          | High priority     |
| Management              | ⚠️ HR-heavy          | Medium–High       |
| Business Administration | ⚠️ Implicit only     | Medium            |
| QAMO                    | ❌ None               | Medium–High       |
| Marketing               | ✅ Strong             | None              |
| Finance                 | ✅ Strong             | None              |
| IS                      | ✅ Strong             | None              |
| Ops & Supply Chain      | ✅ Strong             | None              |

---

## Disciplines with Weak or No Dedicated Dataset Coverage

### 1. **Accounting** ⚠️ (Major Gap)

**Current state:**
No dataset explicitly centered on accounting decisions.

**Why this is a problem:**
Accounting students often think analytics = “forecasting and ML,” not:

* Controls
* Compliance
* Audit risk
* Financial integrity

They don’t see themselves in churn or sentiment analysis.

**Missing Dataset Themes:**

* General ledger transactions
* Journal entries with anomalies
* Expense reimbursements
* Audit flags or SOX controls
* Revenue recognition timing

**Example Dataset Ideas:**

* `general_ledger_transactions.csv`
* `expense_reports_with_fraud_flags.csv`
* `audit_anomaly_log.csv`
* `monthly_close_variance.csv`

**Pedagogical payoff:**
Perfect for EDA, anomaly detection, clustering, ethics, and governance discussions.

---

### 2. **Entrepreneurship** ⚠️ (Conceptual Gap)

**Current state:**
Datasets exist that *could* be used, but none are framed entrepreneurially.

**Why this matters:**
Entrepreneurs think in terms of:

* Uncertainty
* MVP testing
* Resource constraints
* Market validation

Your datasets mostly assume **established firms**.

**Missing Dataset Themes:**

* Early customer experiments
* A/B testing results
* Startup funnel metrics
* Pivot vs persevere signals
* Burn rate vs traction

**Example Dataset Ideas:**

* `startup_mvp_experiments.csv`
* `early_user_cohort_metrics.csv`
* `pricing_test_results.csv`
* `pitch_outcomes_and_metrics.csv`

**Pedagogical payoff:**
Supports regression, classification, and *decision framing under uncertainty*.

---

### 3. **Management (Organizational / Strategy Focus)** ⚠️

**Current state:**
Some HR datasets exist, but **management ≠ HR**.

**Why this is a problem:**
Management students care about:

* Performance
* Coordination
* Culture
* Change management
* Strategy execution

They don’t naturally map this to churn or clustering.

**Missing Dataset Themes:**

* Team performance over time
* OKRs or KPIs
* Change initiative outcomes
* Managerial decision logs
* Cross-team dependencies

**Example Dataset Ideas:**

* `team_performance_kpis.csv`
* `organizational_change_outcomes.csv`
* `manager_decision_effectiveness.csv`
* `employee_engagement_by_team.csv`

**Pedagogical payoff:**
Great for longitudinal analysis, causal thinking, and interpretation.

---

### 4. **Business Administration (Generalist)** ⚠️

**Current state:**
Implicitly covered, but **not explicitly represented**.

**Why this matters:**
Generalist students struggle most with:

> “What is *my* analytic problem?”

They need **cross-functional datasets** that show trade-offs.

**Missing Dataset Themes:**

* Firm-level dashboards
* Balanced scorecard metrics
* Cross-functional trade-offs
* Strategy vs operations tensions

**Example Dataset Ideas:**

* `company_operating_dashboard.csv`
* `balanced_scorecard_metrics.csv`
* `cross_functional_tradeoffs.csv`

**Pedagogical payoff:**
Perfect for CRISP-DM framing, EDA, and communication exercises.

---

### 5. **QAMO (Economics / Market Design)** ⚠️

**Current state:**
Surprisingly underrepresented given the analytical depth of the major.

**Why this matters:**
QAMO students expect:

* Causal inference
* Market structure
* Strategic interaction
* Econometrics, not just ML

Your datasets lean micro-customer, not **market-level**.

**Missing Dataset Themes:**

* Pricing competition
* Supply–demand dynamics
* Policy interventions
* Market entry/exit
* Strategic games

**Example Dataset Ideas:**

* `market_pricing_competition.csv`
* `supply_demand_equilibrium.csv`
* `policy_intervention_outcomes.csv`
* `platform_marketplace_data.csv`

**Pedagogical payoff:**
Excellent for regression, assumptions, and model critique.

---

## Disciplines Well Covered (No Immediate Action Needed)

✔ Marketing
✔ Finance
✔ Information Systems
✔ Operations & Supply Chain

These already have strong, visible dataset anchors.

---


