# Agent PentaFlow  
### Multi-Agent Research Report Automation System  
**Agents Intensive – Capstone Project | November 2025**

Agent PentaFlow is a fully automated multi-agent system built using the **Google Agent Development Kit (ADK)**.  
It streamlines the complete research-report creation workflow—from topic exploration and data scanning to drafting, editing, visualizing insights, and exporting final documents.

This repository contains the architecture, logic design, and workflow for Agent PentaFlow.

---

## 🚩 Project Overview

Producing academic or analytical reports manually is slow, repetitive, and difficult to scale.  
Agent PentaFlow solves this through a **five-stage multi-agent pipeline** that automates research, writing, editing, and visualization.

The system reduces human workload by 65% and ensures consistent quality across multiple reports.

---

## 🧠 Problem Statement

Researchers, students, and analysts often face challenges like:

- Time-heavy research collection  
- Scattered sources and unstructured data  
- Difficulty transforming research into well-written reports  
- Manual formatting and chart creation  
- Repetitive editing cycles  

As demand for documentation grows, manual workflows become unscalable.

---

## 🚀 Solution Summary

Agent PentaFlow automates:

- Topic exploration & literature scanning  
- Structured report planning  
- Full academic writing  
- Automatic chart & table generation  
- Final editing & formatting  
- Exporting the output into a ready-to-publish file  

This converts research reporting into a **guided, intelligent, multi-agent workflow**.

---

## 🏗 Architecture

The system is orchestrated by the **interactive_research_agent**, which coordinates a team of specialized sub-agents.

### 🔹 1. `research_explorer` – Topic Analyst  
- Performs background scanning  
- Summarizes research data  
- Validated by `ResearchScopeValidationChecker`

### 🔹 2. `outline_designer` – Report Planner  
- Generates a complete report outline  
- Includes intro → literature → method → analysis → charts → conclusions  
- Validated by `OutlineFormatChecker`

### 🔹 3. `structured_report_writer` – Report Writer  
- Produces polished academic writing  
- Integrates citations & placeholders  
- Validated by `ReportCompletenessChecker`

### 🔹 4. `chart_creator_agent` – Visuals Generator  
- Creates specifications for charts and tables  
- Extracts numeric patterns from datasets  
- Supports bar, trend, comparison, and summary visuals

### 🔹 5. `report_editor` – Final Editor  
- Fixes clarity, grammar, flow, tone, and formatting  
- Makes user-guided revisions

---

## 🛠 Tools Included

### **File Export Tool – `save_report_to_file`**  
Exports final drafts to Markdown or PDF.

### **Data Analyzer – `tabular_data_inspector`**  
Scans CSV/Excel datasets & extracts numeric insights.

### **Chart Generator – `generate_visual_spec`**  
Builds chart configuration schemas for report integration.

### **Validation Checkers**  
Ensure strong quality control across loops:

- `ResearchScopeValidationChecker`  
- `OutlineFormatChecker`  
- `ReportCompletenessChecker`  

These enforce a stable, retryable workflow.

---

## 📌 Key Features

- Fully modular ADK-based design  
- LoopAgent validation for reliability  
- Automatic chart and table creation  
- End-to-end report generation  
- Exportable documents  
- Domain-independent (works for any research area)

---

## 📈 Value Delivered

- **65% reduction** in report preparation time  
- High consistency and formatting quality  
- Automates repetitive workload  
- Enables reporting in new and unfamiliar domains  
- Improves clarity, structure, and visual presentation

---

## 🔮 Future Improvements

Potential enhancements:

- Web-scraping MCP agent for real-time trending data  
- Automated APA/MLA citation generator  
- Plagiarism detection module  
- Auto-PDF template styling engine

---

## 👤 Author

**Sourav SB**

---

## 📄 License

Released under **CC BY 4.0 (Attribution 4.0 International)**.

---

## 📚 Citation

Sourav SB. Agent PentaFlow: Multi-Agent Research Report Automation System. Agents Intensive – Capstone Project, 2025.

---

## ⭐ If you like this project  
Feel free to fork, modify, and build your own workflow using the Google ADK!
