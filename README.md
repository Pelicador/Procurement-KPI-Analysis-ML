# Procurement KPI Analysis Project Report
#### A Data-Driven Journey to Procurement Excelence

## 1. Executive Summary

### The Challenge That Brought Us Here
Our procurement organization faced mounting pressures in 2022-2023: rising costs, inconsistent supplier performance, and increasing quality complaints from internal stakeholders. With $49.3M in annual procurement spend across 777 purchase orders, we needed answers to critical questions plaguing our operations.

### The Investigation: What We Discovered
Through comprehensive analysis of our procurement data spanning 2022-2023, we uncovered a tale of two procurement worlds. While our negotiation efforts successfully reduced spending from $49.3M to $45.4M—achieving $3.9M in cost savings (7.97% average)—beneath this success story lurked concerning performance disparities that threatened our operational stability.

### The Transformation: Machine Learning Meets Procurement
Our advanced analytics initiative culminated in developing a comprehensive supplier rating system and predictive models achieving 88.7% accuracy in forecasting delivery outcomes. This breakthrough positions us to transform from reactive firefighting to proactive risk management, potentially saving an additional money annually while dramatically reducing operational disruptions.

### The Path Forward: Strategic Recommendations
Our findings demand immediate action on supplier performance management, quality control enhancement, and technology deployment. The data tells a clear story: optimize high-performers, remediate underperformers, and leverage predictive analytics to prevent future challenges.

---

## 2. Project Background

### The Business Problem
Our company and procurement organization began experiencing troubling patterns. Quality complaints increased quarter-over-quarter, delivery delays frustrated internal customers, and cost pressures mounted as market conditions deteriorated. Leadership demanded answers: 
- Are we working with the right suppliers?
- Can we predict/prevent these issues?
- Where are our biggest improvement opportunities?

### The Objective
- **Primary Goal**: Perform an in-depth Exploratory Data Analysis focusing on key procurement KPIs: Cost Savings, Supplier Performance (Delivery time, Defect Rates, Compliance), Item Category Trends, and Order Status insights.
- **Secondary Goal**: Engineer relevant features and KPIs from raw operational data to uncover hidden patterns and relationships.
- **Advanced Goal**: Develop a high-accuracy machine learning model to predict delivery occurrence and critically evaluate performance drivers.

### Stakeholders
- **Procurement Managers**: Needed supplier performance insights and contract negotiation leverage
- **Finance Team**: Required cost optimization opportunities and budget variance explanations
- **Operations**: Demanded delivery reliability improvements and quality assurance
- **Executive Leadership**: Sought strategic supplier relationship guidance and risk mitigation strategies

### Business Context
- **Volume**: 777 purchase orders representing $49.3M in original value
- **Suppliers**: 5 primary suppliers with dramatically different performance profiles
- **Categories**: Electronics, Raw Materials, MRO, Office Supplies, and Packaging
- **Scope**: Global enterprise operations requiring coordinated supplier management

---

## 3. Data Structure and Initial Checks

### Dataset Overview
Our analysis centered on a comprehensive dataset capturing real-world procurement complexity. This anonymized dataset of 777 purchase orders from 2022-2023 reflects genuine operational challenges: supplier delays, compliance gaps, and quality defects that plague modern supply chains.

| Column Name        | Data Type   | Description                                                                |
|--------------------|-------------|----------------------------------------------------------------------------|
| PO_ID              | String / ID | Unique purchase order ID                                                   |
| Supplier           | String      | Anonymized supplier name (e.g., Alpha_Inc)                                 |
| Order_Date         | Date        | Date the order was placed                                                  |
| Delivery_Date      | Date        | Date of delivery (missing for pending/cancelled orders)                    |
| Item_Category      | String      | Item type (Electronics, Raw Materials, Packaging, etc.)                    |
| Order_Status       | String      | Delivered, Pending, Cancelled, or Partially Delivered                      |
| Quantity           | Integer     | Units ordered (includes large orders for bulk procurement)                 |
| Unit_Price         | Float       | Original price per unit                                                    |
| Negotiated_Price   | Float       | Final price post-negotiation                                               |
| Defective_Units    | Integer     | Defects reported post-delivery (missing for unresolved cases)              |
| Compliance         | Boolean     | Adherence to procurement policies (Yes/No)                                 |


### Initial Data Investigations
- **Missing Data Patterns**:
  - **87 missing Delivery_Date values**: Indicated pending/cancelled orders requiring special handling
  - **136 missing Defective_Units records**: Suggested unresolved quality cases, treated as zero defects for initial analysis
  - **1 missing Negotiated_Price**: Single outlier requiring imputation using Unit_Price
- **Data Integrety Validation**:
  - **No negative values** in quantity, prices, or defects—confirming data quality
  - **No instances** where negotiated_price exceeded unit_price—validating negotiation effectiveness
  - **Zero duplicate rows**—ensuring analytical accuracy

### Feature Engineering: Creating Business Intelligence
**Time-Based Analytics**:
- **Lead_time_days**: Calculated delivery performance averaging
- **Temporal Features**: order_year, order_month, order_quarter enabling trend analysis
  
**Financial Intelligence**:
- **Total Value Calculations**: total_value_unit and total_value_negotiated 
- **Savings Metrics**: total_savings, savings_percentage 
- **Price Volatility**: Relative price standard deviation revealing inflation impact
  
**Performance Indicators**:
- **Defect_rate_percentage**: Quality performance averaging
- **Compliance_rate_percentage**: Policy adherence 
- **Delivery_occurred flag**: Binary outcome for predictive modeling

---

## 4. Key Questions for Stakeholders Prior to Project Advancement

### Performance Standards Definition
- What’s an acceptable defect rate by category?
- What compliance rate is considered satisfactory?
- Are there industry benchmarks we should target for average delivery times?

### Supplier Relationship Strategy
- Should all suppliers be weighted equally, or employ different performance standards?
- What constitutes grounds for supplier termination versus performance improvement plans?

### Category Management Approach
- Should negotiation differ by category and how?
- How do we balance volume vs. performance standards across categories?

### Investment
- Should we prioritize short-term cost savings or long-term supplier relationship improvements?
- What budget is available for process improvement? Potential to implement ML model?

---

## 5. Assumptions and Caveats

### Analytical Framework Assumptions
- **Pricing Methodology**: We assumed Negotiated_Price reflects final contract terms rather than initial quotations. 
- **Delivery Performance Interpretation**: Delivery_Date represents actual final delivery rather than scheduled delivery
- **Compliance Scoring Consistency**: We assumed compliance scoring methodology remained consistent across all 777 records and suppliers.

### External Factors Beyond Our Model
- **Market Condition Impact**: Our analysis period (2022-2023) coincided with significant inflation and supply chain disruptions.
- **Category-Specific Limitations**: The high standard deviation in item category pricing may limit the utility of our inflation modeling. Additional data and stakeholder input on specific item price histories would enhance accuracy.

---

## 6. Insights: What the Data Tells Us

### Procurement Efficiency: The Cost Savings Success Story
Our procurement team demonstrated remarkable negotiation skills, reducing total spend from $49.3M to $45.4M. This $3.9M achievement (7.97% average savings) tells a story of skilled procurement professionals maximizing organizational value. However, with an average compliance rate of 82.37%, defective rate of 5.78% and delivery time of 10.80 days, the other KPIs indicate a need to improve operational efficiency.

![Total Procurement Spend](/docs/Total_Procurement.png)
![Other KPI](/docs/Other_KPI_Cards.png)

Category-specific success patterns shows that negotiated procurement efforts led to savings across all categories. The most significant reductions occurred in MRO (from $11.0M to $10.1M) and Office Supplies (from $10.9M to $10.0M), highlighting effective cost control in high-spend areas.

![Procurement Category](/docs/Procurement_Spend_Category.png)

Order fulfillment performance are similar across all five suppliers. Alpha_Inc has the highest delivery rate at 75.89%, while most suppliers (Delta_Logistics, Epsilon_Group, Beta_Supplies, and Gamma_Co) have delivered around 70-72% of their orders. Cancellation rates are relatively low across all suppliers (under 10%), with pending orders ranging from about 10-12% for most suppliers.

![Order Status](/docs/Order_Status_Supplier.png)

Defective rate trending upward indicating potential capacity or reliability issues requiring investigation. The defective rate started around 4% in early 2022, fluctuated between 4-7% throughout most of the period, but then sharply increased to nearly 9% by January 2024, indicating a concerning deterioration in quality control.

![Defective Rate Time](/docs/Defective_Rate_Time.png)


### Supplier Performance Analysis



---

## 7. Machine Learning: Predicting Delivery Success

### Model Goal
Predict whether an order will be delivered based on:
- Supplier, Category, Quantity, Prices, Compliance, Order Date

### Algorithms Tested

| Algorithm             | Accuracy |
|------------------------|----------|
| Gradient Boosting     | 88.70%   ✅ Best |
| Random Forest         | 86.67%   |
| AdaBoost              | 81.16%   |
| SVM                   | 79.42%   |
| Decision Tree         | 78.55%   |
| KNN                   | 76.52%   |
| Logistic Regression   | 70.14%   |
| Naive Bayes           | 67.54%   |

### Business Impact
- Preemptive risk detection before order placement
- Enables better supplier negotiations and internal communication

---

## 8. Recommendations: A Strategic Roadmap

### Immediate (0–30 Days)
**Delta_Logistics Ultimatum**
- Raise compliance to 85%
- Reduce defect rate < 5%
- Submit corrective plan

**Beta_Supplies Quality Fix**
- On-site quality audit
- Incoming inspection protocols

### Mid-Term (30–180 Days)
- **ML Integration**: Risk scoring dashboard + alerts
- **Top Supplier Leverage**: Expand Epsilon/Alpha relationships
- **Category Strategy**:
  - Electronics → Expand
  - Office Supplies → Renegotiate
  - MRO → Leverage volume

### Long-Term (180+ Days)
- Predict price volatility, quality failures, and supplier risk
- Create Procurement Center of Excellence
- Establish ML-based dashboards and reporting

---

## Financial Impact Projections

### Year 1
- **Quality Savings**: $580K
- **Compliance**: $240K
- **Supplier Optimization**: $450K
- **ML ROI**: $150K net benefit

📈 **Total**: $1.42M

### 3-Year Projection
- Year 2: $2.1M
- Year 3: $2.8M
- **Cumulative**: $6.32M
- **ROI**: 380%

---

## Risk Mitigation Framework

### High-Risk Areas
- **Supplier Concentration**: No more than 20% volume to a single supplier
- **Quality Decline**: Deploy predictive defect tracking
- **Compliance Gaps**: Launch auto-monitoring with ML triggers

### Controls

**Tier 1 (Preventive)**
- Supplier diversification
- Real-time quality monitoring
- Pre-approval PO risk scoring

**Tier 2 (Detective)**
- Monthly audits
- Delivery tracking
- Financial health analysis

**Tier 3 (Corrective)**
- Performance improvement plans
- Alternative supplier qualification
- Emergency sourcing protocols

---

## Conclusion: The Case for Action

- **Success**: $3.9M savings and new predictive ML system (88.7% accuracy)
- **Crisis**: Delta_Logistics risk + rising defect trends
- **Call to Action**:
  1. Issue performance ultimatum to Delta_Logistics
  2. Deploy ML system ($150K → $300K savings)
  3. Launch quality improvement plan

🎯 **Outcome**: $6.32M savings, reduced risk, elevated procurement performance

---

_This report marks the beginning of data-driven procurement excellence. The time to act is now._
