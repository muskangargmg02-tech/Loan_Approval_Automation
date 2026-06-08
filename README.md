Based on your PPT, here is a professional **README.md** you can directly use in your GitHub repository.

````md
# AI-Powered Loan Approval Automation

## Overview

AI-Powered Loan Approval Automation is a financial process automation project developed using **n8n**, **Google Sheets**, and **Gmail Integration**. The system automates loan application evaluation by applying predefined credit, debt-to-income (DTI), and AML/PEP compliance rules to streamline decision-making.

This project demonstrates how low-code automation can improve efficiency, reduce operational costs, and enhance compliance in modern lending processes.

---

## Project Objective

Traditional loan approval processes are often slow, expensive, and prone to human error. This project aims to:

- Automate loan application screening
- Reduce approval turnaround time
- Improve consistency in decision-making
- Ensure AML/PEP compliance checks
- Minimize manual intervention

---

## Problem Statement

Manual loan approval processes face several challenges:

- Approval cycles of 3–5 days
- High operational costs
- Human errors in risk assessment
- Limited scalability
- Compliance risks due to manual AML screening

The proposed n8n workflow addresses these issues through intelligent automation.

---

## Technology Stack

- n8n (Workflow Automation Platform)
- Google Sheets (Data Source)
- Gmail API (Email Notifications)
- Rule-Based Decision Engine
- AML/PEP Watchlist Screening

---

## Dataset Details

A custom dataset of **40 loan applications** was created containing:

| Field | Description |
|---------|-------------|
| Application_ID | Unique Loan ID |
| Applicant_Name | Applicant Name |
| Annual_Income_USD | Annual Income |
| Loan_Amount_Requested | Requested Loan Amount |
| Credit_Score | Credit Score (300–850) |
| Debt_To_Income_Ratio | Debt-to-Income Ratio |
| Watchlist_Match_Pct | AML/PEP Match Percentage |
| System_Initial_Action | Initial System Decision |
| Max_Allowable_EMI | Maximum Eligible EMI |
| Decision_Primary_Basis | Reason for Decision |

---

## Workflow Architecture

### Step 1: Trigger Layer
- Manual or Scheduled Trigger
- Reads loan application data from Google Sheets

### Step 2: Rules Evaluation Layer
The workflow evaluates:

- Credit Score
- Debt-to-Income Ratio (DTI)
- AML Watchlist Match

### Step 3: Decision Layer

#### Auto Approve
Conditions:
- Credit Score ≥ 600
- DTI ≤ 0.50
- Watchlist < 0.30

#### Auto Reject
Conditions:
- Credit Score < 560
- OR DTI > 0.55

#### Manual Review
Conditions:
- Watchlist ≥ 0.30 and < 0.80

#### AML Escalation
Conditions:
- Watchlist ≥ 0.80
- OR PEP Match Found

### Step 4: Notification Layer

Automated Gmail notifications:

- Approval Email
- Rejection Email
- Compliance Alert Email
- AML Escalation Email

---

## n8n Workflow Flow

Trigger
↓
Read Google Sheet
↓
Credit & DTI Validation
↓
Decision Routing
├── Auto Approve
├── Auto Reject
├── Manual Review
└── AML/PEP Escalation
↓
Send Email Notifications

---

## Sample Decision Logic

```text
Credit ≥ 600 AND DTI ≤ 0.50 AND Watchlist < 0.30
→ AUTO APPROVE

Credit < 560 OR DTI > 0.55
→ AUTO REJECT

Watchlist ≥ 0.30 AND < 0.80
→ MANUAL REVIEW

Watchlist ≥ 0.80 OR PEP Match
→ AML ESCALATION + REJECTION
````

---

## Workflow Results

Dataset Processed: **40 Applications**

| Decision      | Count |
| ------------- | ----- |
| Auto Approved | 18    |
| Auto Rejected | 11    |
| Manual Review | 11    |

---

## Business Impact

| Parameter        | Manual Process | Automated Process |
| ---------------- | -------------- | ----------------- |
| Processing Time  | 3–5 Days       | < 2 Minutes       |
| Human Effort     | 100%           | 27%               |
| Error Rate       | 35%            | < 3%              |
| Cost/Application | $2400          | $180              |
| Throughput/Day   | 20–30          | 500+              |

### Key Improvements

* 99.9% Faster Processing
* 92% Cost Reduction
* 91% Error Reduction
* 17x Higher Throughput
* 100% AML/PEP Coverage

---

## Challenges & Limitations

* Internet dependency for API connectivity
* Data quality impacts decision accuracy
* Gmail and Google Sheets API rate limits
* Static rule-based decision logic
* Scalability limitations in community edition

---

## Future Scope

### Phase 1

* Automated Audit Logging

### Phase 2

* Machine Learning Credit Scoring
* WhatsApp Notifications
* Multi-Currency Support

### Phase 3

* LLM-Based Risk Assessment
* CRM Integration (Salesforce/HubSpot)

---

## Learning Outcomes

* n8n Workflow Design
* Financial Process Automation
* Risk-Based Decision Systems
* Dataset Engineering
* AML & Compliance Screening
* Business Process Mapping
* FinTech Automation

---

## Repository Structure

```text
loan-approval-automation/
│
├── README.md
├── loan-approval-workflow.json
├── Loan_Approval_Automation.pptx
├── dataset/
│   └── loan_dataset.xlsx
│
├── screenshots/
│   ├── workflow.png
│   ├── gmail-notification.png
│   └── results.png
│
└── documentation/
    └── project-report.pdf
```

---

## Team Members

* Bhumi Gupta
* Muskan Garg
* Manu Bansal
* Vivek
* Sandeep
* Samridhi
* Vansh

---

## Course Information

**MBA Applied Finance**
Financial Technology & Automation

Faculty Guide: **Prof. Lavanya Srivastava**

---

## Conclusion

This project demonstrates how n8n can transform traditional loan approval operations into a scalable, compliant, and intelligent workflow. By automating credit evaluation, AML screening, and customer communication, organizations can significantly improve efficiency while maintaining regulatory compliance.

> "Automation is not about replacing humans — it is about freeing human intelligence for decisions that truly require it."

```

This README is suitable for an MBA project submission, GitHub portfolio, and faculty evaluation.
```
