# Procurement KPI Analysis Project Report

## 1. Executive Summary

### The Challenge That Brought Us Here
Our procurement organization faced mounting pressures in 2022–2023: rising costs, inconsistent supplier performance, and increasing quality complaints. With $49.3M in annual procurement spend across 777 purchase orders, we needed answers.

### The Investigation: What We Discovered
We reduced procurement spend from $49.3M to $45.4M (a $3.9M savings, 7.97%). But we uncovered performance disparities threatening operational stability.

### The Transformation: Machine Learning Meets Procurement
Developed predictive models with 88.7% accuracy in delivery forecasting. A shift from reactive to proactive risk management.

### The Path Forward: Strategic Recommendations
Immediate action on:
- Supplier performance management
- Quality control
- Predictive analytics integration

---

## 2. Project Background

### The Business Problem
Increasing delivery delays, quality complaints, and cost pressures led leadership to question:
- Are we working with the right suppliers?
- Can we predict/prevent these issues?
- Where are our improvement opportunities?

### The Objective
- **Primary Goal**: EDA on key KPIs (Cost Savings, Supplier Performance, Order Trends)
- **Secondary Goal**: Engineer relevant features to uncover patterns
- **Advanced Goal**: Develop a predictive delivery model

### Stakeholders
- **Procurement**: Supplier insights
- **Finance**: Cost optimization
- **Operations**: Delivery reliability
- **Executives**: Strategic supplier guidance

### Business Context
- **Volume**: 777 POs, $49.3M
- **Suppliers**: 5 key vendors
- **Categories**: Electronics, MRO, Packaging, etc.
- **Scope**: Global

---

## 3. Data Structure and Initial Checks

### Dataset Overview
777 purchase orders from 2022–2023 including real-world procurement data.

### Key Findings
- **Compliance Ranges**: 60.82%–98.19%
- **Missing Data**: Delivery dates (87), defects (136)
- **Volume Risk**: Delta_Logistics had highest volume despite worst performance

### Data Architecture
- **Core Fields**: PO_ID, Supplier, Category, Dates, Status
- **Financials**: Unit_Price, Negotiated_Price
- **Quality**: Defective_Units, Compliance

### Feature Engineering
- **Lead Time**: Avg. 10.80 days
- **Total Value**: $49.3M vs $45.4M (negotiated)
- **Defect Rate**: Avg. 5.78%
- **Compliance**: 82.37%
- **Binary Flags**: Delivery occurred

---

## 4. Key Stakeholder Questions

### Performance Standards
- What’s an acceptable defect rate?
- Is 82.37% compliance good enough?

### Supplier Strategy
- Should all suppliers be held to the same standard?
- What are grounds for termination?

### Category Strategy
- Should negotiation differ by category?
- How do we balance volume vs. performance?

### Investment
- Budget for ML deployment?
- Focus: short-term savings or long-term partnerships?

---

## 5. Assumptions and Caveats

### Assumptions
- Negotiated_Price = final contract price
- Delivery_Date = actual delivery (not scheduled)
- Compliance scoring was consistent

### External Factors
- Inflation and supply chain disruption affected pricing
- High category price variability may skew results

---

## 6. Insights: What the Data Tells Us

### Cost Savings Highlights
- **Total Savings**: $3.9M (7.97%)
- **By Category**:
  - Electronics: 12.2% ($9.8M → $8.6M)
  - MRO: 8.2% ($11.6M → $10.7M)
  - Office Supplies: 2.9% ($10.3M → $10.0M)

### Risk & Opportunity
- **High-Risk**: Electronics & Raw Materials (compliance, quality)
- **High-Spend**: MRO = $11.6M (biggest risk if supplier fails)

### Supplier Performance Summary

| Supplier         | Compliance | Defect Rate | Delivery % | Rating |
|------------------|------------|--------------|-------------|--------|
| Epsilon_Group    | 98.19%     | 2.61%         | 72.29%      | 4.40   |
| Alpha_Inc        | 93.62%     | 1.89%         | 75.89%      | 4.20   |
| Gamma_Co         | 86.01%     | ~            | 72.03%      | ~      |
| Beta_Supplies    | 75.64%     | 8.27%         | 70.51%      | ~      |
| Delta_Logistics  | 60.82%     | 10.87%        | 70.18%      | 2.80   |

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
