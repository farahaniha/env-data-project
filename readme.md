
```markdown
# Environmental Data Analysis: A Reproducible Framework

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Power BI](https://img.shields.io/badge/Power%20BI-Ready-yellow)](https://powerbi.microsoft.com)

> **📌 Status:** Data pipeline complete · Dashboards in progress · Final reports due Q1 2027

---

## Table of Contents
- [Overview](#overview)
- [The Gap This Project Addresses](#the-gap-this-project-addresses)
- [Why Global Datasets Matter for the Petroleum Industry](#why-global-datasets-matter-for-the-petroleum-industry)
- [Deliverables](#deliverables)
- [Scope & Data Source](#scope--data-source)
- [Project Structure](#project-structure)
- [Tools & Reproducibility](#tools--reproducibility)
- [Author](#author)

---

## Overview

In environmental monitoring, data is often collected with great effort — yet at the end, it is either left unanalyzed or reduced to basic Excel charts. This project addresses that gap by building a **structured, documented, and reproducible analytical framework** for environmental data, designed to support decision‑making across the energy sector — from ESG analysts and environmental managers to strategic planning teams.

The framework is built to be **bilingual** (Persian/English), ensuring accessibility for both domestic clients (e.g., National Oil Companies) and international stakeholders.

---

## The Gap This Project Addresses

**A concrete example:**  
A typical CO₂ emissions dataset arrives as three mismatched CSV files: one with national totals, one with per‑capita values, and another with sectoral breakdowns — each using different date formats, units, and country naming conventions. Without a standardized pipeline, cross‑comparison is unreliable and time‑consuming.

This project solves that by implementing a clear data lifecycle: from cleaning to visualization.

### Data as an Asset

Beyond the formatting problem, there's a deeper one: environmental data is usually treated as a **compliance obligation** rather than a **reusable asset**. This project treats it as the latter — building a system that transforms raw data into a durable, shareable, and continuously usable resource for decision‑making.

---

## Why Global Datasets Matter for the Petroleum Industry

The petroleum industry operates in a globally interconnected regulatory and environmental landscape. Decisions made in one region affect operations, reputation, and compliance across borders. Access to **standardized, comparable environmental data** is no longer optional — it is a strategic necessity.

**Using publicly available global datasets, this project enables:**

- **Benchmarking environmental performance** against international peers and national targets — using open, verifiable data
- **Supporting ESG reporting** with auditable, transparent data that meets international standards
- **Identifying regional emission trends** — comparing patterns across oil‑producing regions (e.g., Persian Gulf, North America, North Sea) to inform strategic decisions

> 🔍 *The framework is designed to be extensible: the same approach can be applied to proprietary operational data — such as flare gas volumes, produced water quality, or site‑specific emission inventories — once the data structure is aligned.*

---

## Deliverables

- **A clean, standardized data package** ready for analysis
- **A fully documented and reproducible workflow** covering each step from raw data to output
- **Managerial reports and dashboards** for ESG analysts, environmental managers, and strategic planning teams
- **Bilingual delivery** — Persian for domestic clients, English for international stakeholders
- **Technical documentation** for knowledge transfer and future development

---

## Scope & Data Source

- **Primary dataset:** Greenhouse gas and CO₂ emissions data from *Our World in Data*.
- **Time range:** 1990 – present (updated annually).
- **Geographic coverage:** 190+ countries, with a focus on oil‑ and gas‑producing regions (e.g., Persian Gulf, North America, North Sea).
- **Granularity:** National‑level data with sectoral breakdowns where available.
- **Update frequency:** Snapshot‑based analysis. The framework is designed to accommodate updated data with minimal rework.

---

## Project Structure

The project follows a clean, modular structure — each folder has a single responsibility, and the flow is sequential from raw data to final reports.

```
env-data-project/
├── 00_data/                    # All data: raw, cleaned, and metadata
│   ├── raw/                    # Original, unmodified datasets
│   ├── cleaned/                # Processed, QA/QC checked data
│   └── metadata/               # Data dictionaries, source descriptions, unit definitions
│
├── 01_notebooks/               # Jupyter notebooks — numbered in execution order
│   ├── 01_data_cleaning.ipynb  # Load → clean → standardize → export to /cleaned
│   ├── 02_exploratory_analysis.ipynb
│   ├── 03_trend_analysis.ipynb
│   └── 04_comparative_analysis.ipynb
│
├── 02_visualization/           # All visualization outputs
│   ├── exports/
│   │   ├── figures/            # Static figures (PNG, PDF) — used in reports
│   │   └── interactive/        # Interactive Plotly outputs (HTML)
│   ├── dashboard_data/         # Cleaned, shaped data for Power BI
│   └── dashboard.pbix          # Power BI dashboard file (in progress)
│
├── 03_managerial_reports/      # Final reports for stakeholders
│   ├── final_report_fa.pdf     # Full Persian report
│   ├── executive_summary_fa.pdf
│   ├── final_report_en.pdf     # Full English report (if required)
│   ├── executive_summary_en.pdf
│   └── figures/                # High-resolution images embedded in reports
│
├── 04_technical_reports/       # Technical documentation and methodology
│   ├── qc_guidelines.md        # Data quality control rules
│   ├── data_workflow.md        # Step‑by‑step workflow description
│   ├── assumptions.md          # Key assumptions made during analysis
│   ├── data_dictionary.md      # Full column‑level metadata
│   └── user_guide.md           # How to run the code and reproduce the analysis
│
├── readme.md                   # This file
├── .gitignore                  # Files and folders excluded from version control
└── environment.yml             # Conda environment specification (reproducibility)
```

> 📁 Each folder contains a `README.md` explaining its contents and naming conventions.

---

## Tools & Reproducibility

Reproducibility is a core design principle of this project. Every step — from raw data ingestion to the final dashboard — is versioned, documented, and executable.

### Core Toolchain

| Category | Tools |
|----------|-------|
| **Language & Analysis** | Python 3.9+ with Pandas, NumPy, Matplotlib, Seaborn, Plotly |
| **Notebook Environment** | Jupyter Notebook (`jupyter`) |
| **Data Visualization** | Power BI (dashboard), Plotly (interactive charts), Matplotlib/Seaborn (static charts) |
| **Data Storage** | CSV (processed), Excel (metadata), `.pbix` (dashboard) |
| **Package & Environment Management** | Conda (`environment.yml`) — ensures exact dependency versions across systems |
| **Version Control** | Git + GitHub — full change history, commit messages, and an auditable trail |
| **Documentation** | Markdown — all documentation is plain text, versioned, and stored alongside code |
| **Task Automation** | *(Optional)* A `Makefile` or shell script can be added to run the full pipeline end‑to‑end — this is a strong reproducibility signal and will be introduced in the next phase of the project |

### How to Reproduce This Analysis

1. **Clone the repository**
   ```bash
   git clone https://github.com/farahaniha/env-data-project.git
   cd env-data-project
   ```

2. **Create and activate the Conda environment**
   ```bash
   conda env create -f environment.yml
   conda activate env-data-project
   ```

3. **Launch Jupyter and run notebooks in numerical order**
   ```bash
   jupyter notebook
   ```
   - Start with `01_data_cleaning.ipynb`
   - Proceed through `02_exploratory_analysis.ipynb`, `03_trend_analysis.ipynb`, and `04_comparative_analysis.ipynb`

4. **Open the Power BI dashboard** (`02_visualization/dashboard.pbix`) — it connects to the cleaned data and refreshes automatically.

> ✅ This process ensures that anyone with access to this repository can fully reproduce the analysis, verify the results, and extend the work with minimal friction.

---

## Author

**Hadi Farahani, PhD**  
Analytical Chemistry · Environmental Data Analysis · Regulatory Compliance

- **18+ years** of experience in environmental monitoring, analytical chemistry, and regulatory science
- Author of **50+ peer-reviewed scientific publications**
- Manager of multiple **national and international environmental projects**, including those funded by the National Iranian Oil Company (NIOC) and Japan International Cooperation Agency (JICA)
- Expertise in translating complex environmental data into **clear, actionable insights** for decision‑makers
- Active researcher in **chemical compliance**, **pollution control**, and **sustainability frameworks**

**Languages:** Persian (native), English (fluent), German (working knowledge)

📧 **Primary:** farahani@ppwr-textile.com · **Backup:** hadifarahani001@gmail.com  
🔗 [GitHub](https://github.com/farahaniha) · [LinkedIn](https://linkedin.com/in/hadi-farahani-phd-47471a17b) · [Google Scholar](https://scholar.google.com/citations?user=7NnrJ54AAAAJ&hl=en)
```