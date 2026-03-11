#  MindBridge — Workforce Analytics Dashboard

> A Power BI dashboard providing end-to-end visibility into workforce composition, employee performance, satisfaction, and attrition across the organization.

![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=flat&logo=powerbi&logoColor=black)
![Version](https://img.shields.io/badge/Version-1.28-blue)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

##  Table of Contents

- [Overview](#overview)
- [Dashboard Pages](#dashboard-pages)
- [Key Metrics & KPIs](#key-metrics--kpis)
- [Data Model](#data-model)
- [Visuals & Charts](#visuals--charts)
- [Filters & Slicers](#filters--slicers)
- [Getting Started](#getting-started)
- [Requirements](#requirements)
- [File Structure](#file-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

**MindBridge** is a human resources analytics dashboard built in Power BI (Cloud, v1.28). It enables HR teams, managers, and executives to explore workforce data across demographics, performance, satisfaction, and turnover — all within an interactive, filterable interface.

The dashboard answers critical business questions such as:

- Where is attrition happening, and why?
- How is performance distributed across departments and demographics?
- What does our workforce look like by age, gender, education, and ethnicity?
- Which employees are at risk, and what patterns predict voluntary exits?

---

## Dashboard Pages

### 1.  Workforce Infographics
The main overview page. Summarizes the **active employee population** across all dimensions — demographics, job level, department, employment mode, and geography.

### 2.  Non-Active Employees
Focused attrition analysis. Tracks employees who have left the organization, their reasons for departure, satisfaction/performance at exit, and turnover trends by department over time.

### 3.  Tooltip 1 *(Supporting Tooltip)*
A drill-through tooltip displaying the **top departments by headcount**. Activates on hover interactions in the main visuals.

### 4.  Tooltip 2 *(Supporting Tooltip)*
A drill-through tooltip showing the **average turnover rate by year for the top 5 departments** — surfaced as a line chart for trend analysis.

---

## Key Metrics & KPIs

| Metric | Description |
|---|---|
| **All Employees** | Total headcount (active and non-active) |
| **Non-Active Employees** | Count of employees who have left |
| **% Non-Active Employees** | Attrition rate as a percentage |
| **Average Age** | Mean employee age (active workforce) |
| **Average Salary** | Mean compensation (active workforce) |
| **Average Performance Rate** | Mean performance score |
| **Average Satisfaction Rate** | Mean satisfaction score |
| **Average Age (Non-Active)** | Mean age at time of departure |
| **Average Salary (Non-Active)** | Mean compensation at time of departure |
| **Average Performance (Non-Active)** | Performance score at exit |
| **Average Satisfaction (Non-Active)** | Satisfaction score at exit |
| **Years at Company (Non-Active)** | Average tenure before departure |
| **Turnover Rate** | Departmental and overall turnover rate |

---

## Data Model

The dataset includes the following fields:

**Employee Attributes**
- `employee_id` — Unique identifier
- `full_name` — Employee name
- `gender` — Gender identity
- `age` — Age at snapshot date
- `race` — Racial/ethnic background
- `education` — Highest education level
- `hire_date` — Date of hire
- `years_at_company` — Tenure in years
- `active_status` — Active or non-active flag

**Job & Compensation**
- `department` — Primary department
- `sub-department` — Sub-department classification
- `job_level` — Seniority level (e.g., Individual Contributor, Manager)
- `employment_mode` — On-site, remote, hybrid
- `salary` — Compensation value
- `State` — Geographic location

**Performance & Engagement**
- `performance_rate` — Performance evaluation score
- `satisfaction_rate` — Employee satisfaction score
- `tenure` — Duration in current role

**Attrition**
- `term_type` — Voluntary vs. involuntary termination
- `term_reason` — Specific reason for departure
- `Termination Type Flaged` — Flagged termination classification
- `turnover_rate` — Computed turnover rate
- `year` — Year of termination

---

## Visuals & Charts

### Workforce Infographics Page

| Visual | Type | Insight |
|---|---|---|
| All Employees | KPI Card | Total headcount |
| Average Performance Rate | Gauge | Org-wide performance benchmark |
| Average Satisfaction Rate | Gauge | Org-wide satisfaction benchmark |
| Employee Presence by State | Shape Map | Geographic workforce distribution |
| Workforce by Job Level | Bar Chart | IC vs. manager composition |
| Employment Mode Distribution | 100% Stacked Column | On-site vs. hybrid vs. remote |
| Workforce by Department | Bar Chart | Headcount by department |
| Education Level Distribution | Clustered Bar Chart | Degree attainment breakdown |
| Age Distribution | Clustered Column Chart | Age range concentration |
| Gender Distribution | Donut Chart | Gender representation |
| Employees by Position & Gender | Column Chart | Gender split by job level |
| Race/Ethnicity Distribution | 100% Stacked Bar | Ethnic composition |

### Non-Active Employees Page

| Visual | Type | Insight |
|---|---|---|
| Average Performance Rate (Non-Active) | Gauge | Performance at exit |
| Average Satisfaction Rate (Non-Active) | Gauge | Satisfaction at exit |
| Turnover by Department | Bar Chart | Top departments for attrition |
| Satisfaction vs. Performance | Scatter Chart | Correlation at exit |
| Termination Type Breakdown | Donut Chart | Voluntary vs. involuntary split |
| Exit Reasons | Bar Chart | Top reasons for voluntary departure |
| Employee Table | Table | Detailed non-active employee list |

---

## Filters & Slicers

Both main pages include interactive slicers to filter all visuals simultaneously:

- **Year** — Filter by hire or termination year
- **Department** — Filter by organizational department
- **Gender** — Filter by gender identity
- **Employment Mode** — On-site / Hybrid / Remote
- **Job Level** — Seniority / role classification

A **Clear Filters** button is included on each page to reset all selections instantly.

---

## Getting Started

### Prerequisites

- [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) (latest recommended)
- Or access to **Power BI Service** (cloud)

### Opening the Dashboard

1. Clone or download this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/mindbridge-dashboard.git
   ```
2. Open `Dashboard_for_MindBridge.pbix` in Power BI Desktop.
3. If prompted, update the **data source path** to point to your local data file.
4. Click **Refresh** to load the latest data.

### Publishing to Power BI Service

1. Open the `.pbix` file in Power BI Desktop.
2. Click **Home → Publish**.
3. Select your target workspace.
4. Access via `app.powerbi.com`.

---

## Requirements

| Tool | Version |
|---|---|
| Power BI Desktop | 2.0+ (created in 2025.11 cloud release) |
| Power BI Service | Any current plan |
| Data Format | As connected (CSV / Excel / database) |

>  This file was created using **Power BI Cloud (v1.28)**. Some features may not render correctly in older versions of Power BI Desktop.

---

## File Structure

```
mindbridge-dashboard/
│
├── Dashboard_for_MindBridge.pbix   # Main Power BI report file
├── README.md                        # This file
├── data/
│   └── (source data files here)    # CSV / Excel source data
├── assets/
│   └── screenshots/                # Dashboard preview images
│       ├── workforce-infographics.png
│       └── non-active-employees.png
└── docs/
    └── data-dictionary.md          # Field definitions and business rules
```

>  Add your source data files to the `/data` folder and update the Power BI data source connection accordingly.

---

## Screenshots

> *(Add screenshots of your dashboard pages here)*

| Workforce Infographics | Non-Active Employees |
|---|---|
| ![page1](assets/screenshots/workforce-infographics.png) | ![page2](assets/screenshots/non-active-employees.png) |

---

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit changes: `git commit -m "Add: description of change"`
4. Push to branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

---

## License

This project is licensed under the [MIT License](LICENSE).

---

*Built with using Microsoft Power BI*
