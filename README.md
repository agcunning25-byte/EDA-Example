# iFood CRM Case Study: Enhancing Marketing ROI with EDA and Statistical Testing

## Project Overview & Business Problem

This project is a comprehensive analysis of a customer dataset from **iFood**, a leading Brazilian online food retailer. 

The core business problem is that previous marketing campaigns resulted in a net financial loss, indicating a critical need for more effective customer targeting. The objective of this analysis is to move beyond simple demographic targeting and identify the key behavioral and engagement drivers that correlate with campaign response.

By applying a structured workflow of data cleaning, exploratory data analysis (EDA), and statistical hypothesis testing, this project uncovers actionable insights to help iFood improve marketing ROI by focusing on high-response customer segments.

## Dataset

The analysis is based on a snapshot of **2,240 customers**, collected between 2012 and 2014. The dataset includes a rich mix of customer attributes:
* **Demographics:** Age, Education, Marital Status, Income
* **Purchase History:** Spending across six categories (e.g., Wine, Meat, Fruits)
* **Engagement Metrics:** Recency of last purchase, total website visits
* **Campaign History:** Responses to five previous marketing campaigns

## Analysis Workflow & Skills Demonstrated

This project showcases an end-to-end data analysis workflow, from initial data ingestion to final, actionable recommendations.

### 1. Data Cleaning & Feature Engineering
* **Data Integrity:** Handled missing values (e.g., in `Income`) and managed data types.
* **Feature Creation:** Engineered new, more insightful features from raw data, such as:
    * `Age` (from `Year_Birth`)
    * `Total_Purchases` (summing all product categories)
    * `Customer_Tenure` (time since enrollment)
    * `Overall_Campaign_Response` (total campaigns accepted)

### 2. Exploratory Data Analysis (EDA)
* **Univariate & Bivariate Analysis:** Deeply analyzed the distributions and relationships of key variables, including customer demographics, purchasing habits, and engagement.
* **Visualization:** Used `matplotlib` and `seaborn` to visualize patterns, identifying clear differences in spending and behavior between customer segments (e.g., high vs. low-income, responders vs. non-responders).
* **Initial Findings:** The EDA process revealed that behavioral and spending data (like wine purchases and recency) appeared to be more strongly correlated with campaign response than static demographic data.

### 3. Statistical Hypothesis Testing
* **Validating Insights:** Moved beyond simple observation to statistically validate key hypotheses.
* **Example Hypothesis:** A key question was whether digital engagement truly translated to purchasing behavior.
    * **Hypothesis:** Customers with 10 or more website visits make *fewer* purchases than those with fewer than 10 visits.
    * **Test:** A **one-tailed t-test** was performed to compare the means of the two groups.
    * **Result:** The test was **statistically significant (t = -2.808, p = 0.002)**. We rejected the null hypothesis, providing strong evidence that customers with very high web visits are, in fact, *less* likely to purchase, possibly indicating a "window shopper" segment.

## Key Findings & Actionable Insights

This analysis successfully identified clear, data-driven factors that predict campaign success:

1.  **Behavior Outweighs Demographics:** The strongest predictors of campaign response are not *who* a customer is (demographics) but *what they do* (behaviors).
2.  **Key Predictive Features:**
    * **Wine Spending:** Customers with higher spending on wine are significantly more likely to respond positively to campaigns.
    * **Recency:** Customers who have purchased more recently are a much better target.
    * **Past Engagement:** A customer's history of responding to past campaigns is a very strong predictor of future response.
3.  **The "Window Shopper" Paradox:** As confirmed by the t-test, high digital engagement (10+ visits) does *not* equal high purchase intent. This segment requires a different marketing strategy focused on conversion, not just promotion.

## Conclusions & Recommendations

To improve marketing ROI, iFood should shift its strategy from broad, demographic-based campaigns to a more targeted, behavioral segmentation approach.

* **Primary Target Segment:** Focus marketing spend on customers with a proven history of high wine/meat spending, high recency, and any past campaign acceptances.
* **Re-engagement Segment:** Develop a separate, lower-cost campaign (e.g., specific discounts, reminders) for the "high-visit, low-purchase" segment to nudge them toward conversion.
* **Ignore Segment:** Deprioritize marketing spend on customers with low tenure, low past purchases, and no prior campaign engagement.

## Technologies Used

* **Python**
* **Pandas & NumPy** for data manipulation and cleaning.
* **Matplotlib & Seaborn** for data visualization and EDA.
* **SciPy (scipy.stats)** for performing the t-test and statistical analysis.
