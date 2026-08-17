# 📊 Customer Churn Analysis

An end-to-end **Customer Churn Analysis** project focused on identifying customer retention patterns, high-risk customer segments, revenue exposure, and potential churn drivers using **Python, SQL, Pandas, and data visualization**.

The project combines customer, subscription, and customer-support data to generate actionable business insights and retention strategies.

---

## 📌 Project Overview

Customer churn is a critical business problem for subscription-based companies because losing customers directly impacts recurring revenue and long-term customer value.

This project analyzes customer behavior and subscription patterns to answer key business questions such as:

* What is the overall customer churn rate?
* Which subscription plans have the highest churn?
* Which states have the highest churn rates?
* How does churn vary across subscription acquisition channels?
* How much monthly revenue is exposed to churn?
* What is the average customer tenure and ARPU?
* Is there a relationship between support escalations and customer churn?
* Which customers should be prioritized for retention?
* What actions can the business take to reduce avoidable churn?

---

## 🎯 Business Objective

The primary objective of this project is to:

> **Identify customer churn patterns, quantify revenue exposure, understand potential churn drivers, and provide data-driven recommendations to improve customer retention.**

---

## 🗂️ Dataset Structure

The analysis uses data from three related tables stored in a SQLite database:

### 1. Customer Data

Contains customer-level demographic and geographic information.

Key fields include:

* Customer ID
* Customer Name
* Country
* State
* Gender
* Date of Birth

### 2. Subscription Data

Contains subscription and financial information.

Key fields include:

* Customer ID
* Subscription Start Date
* Subscription Type
* Renewal Date
* Plan Type
* Contract Type
* Cancellation Date
* Cancellation Reason
* Monthly Charges
* CLTV
* Churn Score

### 3. Support Data

Contains customer support and complaint information.

Key fields include:

* Customer ID
* Complaint Date
* Escalations
* CSAT Score
* Customer Comments

The three datasets are integrated using **Customer ID** to create a unified analytical dataset.

---

## 🛠️ Technologies Used

| Technology           | Purpose                                |
| -------------------- | -------------------------------------- |
| **Python**           | Data analysis and processing           |
| **Pandas**           | Data manipulation and transformation   |
| **NumPy**            | Numerical operations                   |
| **SQLite**           | Database querying and data integration |
| **Matplotlib**       | Data visualization                     |
| **Seaborn**          | Statistical visualization              |
| **Jupyter Notebook** | Analysis and documentation             |

---

## 🔄 Project Workflow

```text
SQLite Database
      ↓
Data Extraction
      ↓
Data Cleaning & Standardization
      ↓
Feature Engineering
      ↓
Data Integration
      ↓
Exploratory Data Analysis
      ↓
Business Metrics
      ↓
Data Visualization
      ↓
Customer Risk Segmentation
      ↓
Business Insights & Recommendations
```

---

## 🧹 Data Cleaning

The following data-cleaning activities were performed:

* Inspected database tables and column structures
* Checked data types and missing values
* Renamed columns for better readability
* Removed unnecessary columns
* Converted date fields into datetime format
* Standardized gender categories
* Handled missing country values using state-based mapping
* Removed unnecessary support-data columns
* Converted complaint and subscription dates into appropriate datetime formats

---

## ⚙️ Feature Engineering

Several analytical features were created to support the analysis.

### Churn Indicator

A binary `churned` column was created:

```text
1 → Customer has cancelled the subscription
0 → Customer has not cancelled the subscription
```

### Customer Tenure

Customer tenure was calculated using the subscription start date and cancellation/reference date.

### Complaint Count

The number of complaints associated with each customer was calculated from the support dataset.

### Churn Risk

Customers were segmented using the existing churn score:

| Churn Score | Risk Category |
| ----------: | ------------- |
|        < 50 | Low           |
|       50–69 | Medium        |
|        ≥ 70 | High          |

---

# 📈 Key Business Metrics

| Metric                           |                    Result |
| -------------------------------- | ------------------------: |
| **Overall Churn Rate**           |                 **27.4%** |
| **Retention Rate**               |                 **72.6%** |
| **Churned Customers**            |             **137 / 500** |
| **Average Customer Tenure**      | **1,105 days (~3 years)** |
| **ARPU**                         |          **₹13.74/month** |
| **Monthly Revenue at Risk**      |             **₹1,740.63** |
| **Escalation Rate**              |                 **11.4%** |
| **Average Complaints per User**  |                  **0.29** |
| **Escalation–Churn Correlation** |                  **0.25** |

---

# 🔎 Key Insights

### 1. Overall Customer Churn

The overall churn rate is **27.4%**, meaning **137 out of 500 customers** have churned.

This indicates a significant customer-retention challenge and provides an opportunity for targeted retention initiatives.

---

### 2. Basic Plan Has the Highest Churn

Churn varies significantly across subscription plans:

| Plan      | Churn Rate |
| --------- | ---------: |
| **Basic** | **31.42%** |
| Standard  |     25.51% |
| Premium   |     20.51% |

The **Basic plan has the highest churn rate**, suggesting that customers on the entry-level plan may require additional retention strategies.

---

### 3. Significant State-Level Variation

The analysis shows substantial differences in churn across states.

The highest observed state-level churn rates include:

| State         | Churn Rate |
| ------------- | ---------: |
| **Meghalaya** | **66.67%** |
| Telangana     |     50.00% |
| Karnataka     |     36.73% |
| West Bengal   |     31.25% |
| Maharashtra   |     30.00% |

Meghalaya represents the highest observed churn rate and should be investigated further to determine whether operational, service, pricing, or customer-support factors are contributing to the result.

---

### 4. Churn by Subscription Type

Churn also varies by customer acquisition/subscription type:

| Subscription Type | Churn Rate |
| ----------------- | ---------: |
| **Paid**          | **33.10%** |
| Organic           |     26.21% |
| Referral          |     22.73% |

Paid customers show the highest churn rate among the three acquisition categories.

---

### 5. Revenue Exposure

The analysis estimates **₹1,740.63 in monthly revenue at risk from customers who have churned**.

This metric helps translate customer churn into a direct financial impact and can be used to prioritize retention initiatives.

---

### 6. Customer Support and Churn

The analysis found a **0.25 positive correlation between escalations and churn**.

This indicates a **mild positive relationship**: customers associated with escalations tend to show somewhat higher churn.

However, correlation does not imply causation, so additional analysis would be required before concluding that escalations directly cause churn.

---

# 📊 Visual Analysis

The project includes visual analysis of:

* Monthly churn trends
* Churn by subscription plan
* Churn by state
* Correlation matrix
* Pairwise relationships between selected variables
* Customer churn-risk segments

These visualizations help identify patterns that are difficult to observe from aggregate metrics alone.

---

# 💡 Business Recommendations

Based on the analysis, the following actions are recommended:

### 1. Investigate the April 2026 Churn Spike

Analyze the April 2026 increase in churn to identify possible:

* Service issues
* Pricing changes
* Customer-support problems
* Renewal-related issues
* Product or operational changes

---

### 2. Prioritize Basic Plan Retention

Since the Basic plan has the highest churn rate at **31.42%**, consider:

* Targeted retention campaigns
* Loyalty incentives
* Plan upgrades
* Improved onboarding
* Personalized offers

---

### 3. Investigate High-Churn States

Conduct a deeper analysis of states such as **Meghalaya and Telangana** to understand regional differences in:

* Customer behavior
* Service quality
* Pricing sensitivity
* Support experience
* Subscription preferences

---

### 4. Prioritize High-Risk Customers

Use churn-risk segmentation along with customer value metrics such as **CLTV** to prioritize customers for proactive engagement.

A potential retention strategy could be:

```text
High Churn Risk + High CLTV
          ↓
Highest Retention Priority
```

---

### 5. Analyze Support Escalations

Since escalations show a positive relationship with churn, recurring complaints and escalated support cases should be investigated to identify preventable customer-experience issues.

---

### 6. Investigate Customer Switching Drivers

Analyze cancellation reasons and benchmark:

* Competitor pricing
* Subscription plans
* Product features
* Contract terms
* Customer experience

This can help identify why customers may be switching to competitors.

---

# 📁 Project Structure

```text
customer-churn-analysis/
│
├── 📓 Churn_Analysis.ipynb
├── 🗄️ customer_churn_db.db
├── 📊 churn_data.csv
├── 📸 insights.png
└── 📖 README.md
```

---

# 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/customer-churn-analysis.git
```

### 2. Navigate to the project directory

```bash
cd customer-churn-analysis
```

### 3. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open

```text
Churn_Analysis.ipynb
```

Make sure the SQLite database file is located in the same directory as the notebook.

---

# 📌 Skills Demonstrated

This project demonstrates practical experience in:

* **SQL & SQLite**
* **Python**
* **Pandas**
* **NumPy**
* **Data Cleaning**
* **Data Transformation**
* **Feature Engineering**
* **Exploratory Data Analysis (EDA)**
* **Statistical Analysis**
* **Data Visualization**
* **Correlation Analysis**
* **Customer Segmentation**
* **Business Intelligence**
* **KPI Analysis**
* **Revenue Impact Analysis**
* **Data-Driven Business Recommendations**

---

# 🔮 Future Improvements

Potential extensions to this project include:

* Build a machine-learning model to predict customer churn
* Compare multiple classification algorithms
* Perform feature importance analysis
* Build an interactive **Power BI dashboard**
* Add customer lifetime value analysis
* Perform cohort-based retention analysis
* Analyze cancellation reasons in greater detail
* Develop a customer retention scoring framework
* Add automated SQL-based reporting

---

# 📌 Project Takeaway

This project demonstrates how customer, subscription, and support data can be transformed into actionable business insights.

Rather than focusing only on the churn percentage, the analysis connects churn with **subscription plans, geography, customer support, revenue exposure, customer tenure, and risk segmentation** to help businesses identify where retention efforts should be prioritized.

---

## 👨‍💻 Author

**Deepanshu Yadav**

BCA Graduate | Aspiring Data Analyst

### Areas of Interest

* Data Analytics
* Business Intelligence
* Machine Learning
* Customer Analytics
* Data Visualization

---

⭐ If you found this project useful, consider giving the repository a star!
