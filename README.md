# Grant Application Management System (GAMS) - Technology Prototype

**CSE 499 Senior Project**  
**Student:** Israel Brown  
**Institution:** Brigham Young University - Idaho  
**Stakeholder:** Ministry of Labour & Social Security, Jamaica

---

## 🎯 Prototype Purpose

This technology prototype demonstrates the **core workflow engine** that will power the Grant Application Management System (GAMS). It validates that the fundamental concepts work before building the full web application.

**This is NOT the final product** - it's a learning tool to:
- Prove the workflow state machine concept works
- Test with real Ministry data (2,313 applications)
- Identify processing time bottlenecks
- Validate analytics requirements
- Demonstrate dashboard visualization capabilities

---

## 📊 What This Prototype Demonstrates

### ✅ 1. **Data Integration**
Successfully loads and processes 2,313 real grant applications from the Ministry of Labour & Social Security's Hanover Rehabilitation Program database.

### ✅ 2. **Workflow State Machine**
Implements an 8-state workflow engine with defined transitions:
- Submitted
- Assigned to Social Worker
- Under Review
- Submitted to Head Office
- Under Head Office Review
- Approved
- Declined
- Payment Issued

**Key Feature:** The system enforces valid state transitions, preventing invalid workflow moves (e.g., can't jump from "Submitted" directly to "Payment Issued").

### ✅ 3. **Status Normalization**
Maps various status descriptions in the legacy data to standardized workflow states, ensuring consistency across the system.

### ✅ 4. **Workflow Analytics**
Calculates average processing times for each workflow stage:
- Submission to social worker assignment
- Social worker review duration
- Review to head office submission
- Head office processing time

### ✅ 5. **Admin Dashboard**
Generates visual analytics showing:
- Application status distribution (pie chart)
- Top 10 grant types (bar chart)
- Applications by parish (geographic distribution)
- Application volume trends over time (line chart)

### ✅ 6. **Role-Based Analytics**
Analyzes workload distribution across social workers, identifying:
- Top 10 social workers by caseload
- Average applications per social worker
- Opportunities for better load balancing

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

### Installation

**Windows (VSCode):**
```bash
# Install required libraries
python -m pip install pandas matplotlib openpyxl

# Run the prototype
python gams_prototype.py
```

**Mac/Linux:**
```bash
# Install required libraries
pip install pandas matplotlib openpyxl

# Run the prototype
python gams_prototype.py
```

**Note:** On Windows, if `pip` is not recognized, always use `python -m pip` instead.

### Expected Output
The prototype will:
1. Load 2,313 grant applications from the Excel database
2. Analyze workflow states and processing times
3. Demonstrate the state machine with sample applications
4. Analyze social worker workload
5. Generate a visual dashboard (`gams_dashboard.png`)
6. Display a comprehensive summary report

**Runtime:** Approximately 10-15 seconds

---

## 🔑 Key Findings from Real Data

### Processing Time Analysis
Based on 2,313 real applications from the Ministry:

- **Overall:** Current system shows extended processing times
- **Workflow Stages:** Multiple bottlenecks identified across the process
- **Opportunity:** Automation can significantly reduce delays

### Workflow Insights
- **79.5%** of applications are "Under Review" (potential backlog)
- **20.4%** are "Declined" 
- **<1%** have reached "Approved" status in the dataset

### Social Worker Workload
- **Uneven distribution:** Top social worker handles 465 applications while others handle <100
- **Opportunity:** GAMS can implement automated workload balancing
- **Issue:** Some social workers have duplicate entries (case sensitivity issues)

---

## 💡 What I Learned Building This

### Technical Learnings
1. **State Machine Implementation:** Successfully created a workflow engine with valid transition rules
2. **Data Normalization:** Real-world data is messy - status values need standardization
3. **Analytics Design:** Dashboard visualizations are crucial for identifying bottlenecks
4. **Python for Data Analysis:** Pandas and Matplotlib are powerful tools for prototyping

### Business Process Learnings
1. **Processing Times:** Current manual system has significant delays
2. **Workload Distribution:** Manual assignment leads to imbalanced caseloads
3. **Data Quality:** Inconsistent naming (case sensitivity) creates duplicate entries
4. **Visibility Gap:** Lack of real-time dashboards hides systemic issues

---

## 🎯 Next Steps (Full GAMS System)

### Components Still to Build

#### 1. **Web Frontend** (Planned: Weeks 5-6)
- HTML/CSS/JavaScript responsive interface
- Applicant submission forms
- Admin dashboard with real-time updates

#### 2. **RESTful API Backend** (Planned: Weeks 3-5)
- C# .NET 8 API
- Workflow transition endpoints
- Authentication and authorization

#### 3. **PostgreSQL Database** (Planned: Weeks 2-3)
- Schema design based on prototype learnings
- Migration from Excel to proper RDBMS
- Audit logging tables

#### 4. **Email Notification System** (Planned: Week 9)
- SendGrid integration
- Automated notifications at workflow milestones

#### 5. **Role-Based Access Control** (Planned: Week 10)
- Implement RBAC using .NET Identity
- Define permissions for Admin, Social Worker, Applicant, Finance roles

---

## 📈 Success Metrics

### Prototype Success Criteria ✅
- [x] Load real Ministry data (2,313 applications)
- [x] Implement workflow state machine with 8 states
- [x] Enforce valid state transitions
- [x] Calculate processing time analytics
- [x] Generate visual dashboard
- [x] Demonstrate with sample applications
- [x] Identify real-world insights from data

### Full System Success Criteria (To Be Measured)
- [ ] Reduce average processing time by 30%
- [ ] 100% of applications tracked in system
- [ ] Zero lost or misplaced applications
- [ ] Real-time visibility for all stakeholders

---

## 🛠️ Technology Stack

### Current Prototype
- **Language:** Python 3.12
- **Data Analysis:** Pandas
- **Visualization:** Matplotlib
- **Data Source:** Excel (openpyxl)

### Planned Full System
- **Frontend:** HTML, CSS, JavaScript
- **Backend:** C# .NET 8 (ASP.NET Core)
- **Database:** PostgreSQL 15
- **Email:** SendGrid API
- **Hosting:** Render.com (initially)

---

**Last Updated:** February 7, 2026  
**Version:** 1.0 (Technology Prototype)
