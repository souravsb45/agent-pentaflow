Agent PentaFlow — Project Overview

Agents Intensive – Capstone Project

Project Summary

Agent PentaFlow automates the end-to-end creation of research reports using a modular multi-agent architecture. Built with an ADK-inspired design, PentaFlow orchestrates specialized agents to perform topic exploration, outline generation, drafting, visualization, editing, and final export — turning a labor-intensive, multi-step process into a repeatable, reliable pipeline.

The name PentaFlow reflects the system’s five-stage workflow and its focus on structured, validated report production.

Problem Statement

Producing high-quality research reports is time-consuming and error-prone. Common pain points include:

Sourcing and synthesizing literature across many places

Converting raw findings into coherent, properly structured writing

Designing and embedding visuals (charts/tables) from datasets

Repeated editing cycles to improve clarity and tone

Consistent formatting and export to deliverable files

These tasks often consume analysts’ time and mental energy, leaving less room for interpretation, insight, and decision-making. As the volume and frequency of reporting increase—across students, researchers, and enterprise teams—the manual approach does not scale.

Solution Statement

Agent PentaFlow addresses these problems by splitting the reporting process into specialized agents, each with a clear role and validation logic. PentaFlow can:

Automatically research topics and synthesize background context.

Produce a well-structured, editable outline.

Generate a full draft using the approved outline and supporting context.

Automatically create chart specifications and embed recommendations from datasets.

Iterate and polish the output using an editor agent and validation checkers.

Export the final report to Markdown or PDF.

This automation reduces repetitive work, standardizes output quality, and accelerates report delivery while keeping human control over final content.

Architecture

At the center of PentaFlow is the interactive_research_agent — the orchestrator that coordinates specialized sub-agents and tools. The design follows an ADK-like modular pattern enabling extensibility, testability, and robust validation.

Core components

interactive_research_agent — orchestrator / project manager

research_explorer — topic exploration & context summarization

outline_designer — structured outline generator

structured_report_writer — converts outline + context into full drafts

chart_creator_agent — dataset inspector & visualization spec generator

report_editor — final polishing and formatting agent

Tools

tabular_data_inspector — inspects CSV/Excel and returns summary statistics

generate_visual_spec — suggests chart types and configuration schemas

save_report_to_file — exports Markdown/PDF and ensures file structure

Validation Checkers

ResearchScopeValidationChecker — ensures research depth and coverage

OutlineFormatChecker — validates outline completeness and flow

ReportCompletenessChecker — confirms presence of required sections and references

Agents follow a LoopAgent pattern (retry + validate). A checker must pass before the orchestrator proceeds to the next stage.

Agent Roles (Detailed)
research_explorer

Gathers background information, identifies key themes and sources.

Returns a compact, structured context object: summary, key concepts, citation list.

Uses configurable search pipelines (web, academic databases, local corpora).

outline_designer

Produces a section-by-section outline (title, headings, bullet notes, suggested visuals).

Creates versions and accepts feedback for iterative refinement.

Verifies the outline via OutlineFormatChecker.

structured_report_writer

Expands the approved outline into full prose: paragraphs, subheadings, transitions.

Integrates code snippets, formulas, and contextual citations when provided.

Works in multiple tones (academic, business, or executive summary).

chart_creator_agent

Parses uploaded datasets using tabular_data_inspector.

Identifies numeric patterns and proposes visualization specs (bar, line, scatter, summary table).

Outputs chart specs and optionally generated image files (if plotting tools are available).

report_editor

Polishes grammar, clarity, and style; applies consistent formatting.

Incorporates user feedback and iterates until approval.

Ensures the final document conforms to the project style guide.

Workflow

User supplies topic (and optionally a dataset or codebase).

research_explorer gathers context and returns a structured summary.

outline_designer generates an outline and solicits user approval.

On approval, structured_report_writer generates a first draft.

If data provided, chart_creator_agent produces visualization specs and assets.

report_editor polishes draft; validation checks ensure completeness.

save_report_to_file exports the final Markdown/PDF.

Optionally, a social-media-agent or delivery tool (external) publishes or schedules the output.

Each stage uses checkers to either escalate success or request a retry with additional prompts, ensuring a robust, high-quality pipeline.

Demo (Simplified)

Provide topic: Impact of Renewable Energy Adoption in India

PentaFlow runs: research → outline → draft → visuals → edit → export

Final artifact: outputs/Impact_of_Renewable_Energy.md + optional outputs/charts/*.png

A demo notebook and runner script (scripts/run_pipeline.py) are included to simulate this flow locally.

The Build — Tools & Technologies

Language: Python 3.11+

Design pattern: ADK-inspired modular agents + LoopAgent validation pattern

Libraries (examples): pandas, matplotlib/plotly (for visuals), PyYAML (configs)

Testing: pytest for basic pipeline tests

Export: Markdown and optional PDF via pandoc or python-markdown pipelines

The repository contains moderately detailed templates for each agent and tool so teams can replace LLM placeholders with actual ADK/LLM calls.

Project Structure (recommended)
Agent-PentaFlow/
├── README.md
├── LICENSE
├── docs/
│   └── architecture.md
├── src/
│   ├── main/
│   │   ├── orchestrator/interactive_research_agent.py
│   │   ├── agents/
│   │   ├── checkers/
│   │   └── tools/
│   └── tests/
├── examples/
│   ├── sample-dataset.csv
│   └── demo.ipynb
├── scripts/
│   └── run_pipeline.py
└── outputs/

Installation

Clone the repo:

git clone https://github.com/your-username/agent-pentaflow.git
cd agent-pentaflow


Create a virtual environment and install dependencies:

python -m venv .venv
source .venv/bin/activate      # macOS/Linux
.venv\Scripts\activate         # Windows

pip install -r requirements.txt


(The sample repo includes a minimal requirements.txt. Add ADK/LLM client libraries as needed.)

Running the Agent (local simulation)

A provided runner script demonstrates the end-to-end flow using template agents.

python scripts/run_pipeline.py --topic "Impact of Renewable Energy" --dataset examples/sample-dataset.csv


Outputs: outputs/<topic>.md and visualization specs under outputs/charts/.

Tests

Run the basic test suite:

pytest -q


Tests ensure the orchestrator returns a generated path and the runner writes the output file.

Value Statement

Agent PentaFlow reduces time spent on report preparation by automating research, drafting, visuals, and editing. This increases throughput and allows teams to focus on interpretation and strategic decisions. Early tests show reliable draft generation and consistent formatting — a significant productivity boost for researchers and analysts.

Future Work

Planned improvements include:

Real ADK integration and agent-level LLM calls.

Real-time web-scraper agent for trend detection.

Citation manager (APA/MLA), and plagiarism checking.

UI dashboard for interactive approval and edits.

Cloud storage and multi-user collaboration features.

Author & Citation

Author: Sourav SB

Citation:

Sourav SB. Agent PentaFlow: Multi-Agent Research Report Automation System. Agents Intensive – Capstone Project, 2025.

License

Released under Creative Commons Attribution 4.0 International (CC BY 4.0).
