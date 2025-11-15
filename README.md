# agent-pentaflow
A multi-agent research automation system built with the Google ADK that generates end-to-end research reports with structured writing, data analysis, charts, and document export.
Agent-PentaFlow/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── architecture.md
│   ├── workflow-diagram.png
│   ├── agents-overview.md
│   ├── tools-and-checkers.md
│   └── examples/
│       ├── sample-report.md
│       └── sample-charts/
│
├── src/
│   ├── main/
│   │   ├── orchestrator/
│   │   │   └── interactive_research_agent.py
│   │   ├── agents/
│   │   │   ├── research_explorer.py
│   │   │   ├── outline_designer.py
│   │   │   ├── structured_report_writer.py
│   │   │   ├── chart_creator_agent.py
│   │   │   └── report_editor.py
│   │   ├── checkers/
│   │   │   ├── research_scope_validation_checker.py
│   │   │   ├── outline_format_checker.py
│   │   │   └── report_completeness_checker.py
│   │   ├── tools/
│   │   │   ├── save_report_to_file.py
│   │   │   ├── tabular_data_inspector.py
│   │   │   └── generate_visual_spec.py
│   │   └── config/
│   │       └── settings.yaml
│   │
│   └── tests/
│       ├── test_research_explorer.py
│       ├── test_outline_designer.py
│       ├── test_report_writer.py
│       ├── test_chart_creator.py
│       └── test_editor.py
│
├── examples/
│   ├── input-data/
│   │   ├── sample-dataset.csv
│   │   └── sample-topic.txt
│   ├── outputs/
│       ├── final-report.md
│       ├── final-report.pdf
│       └── charts/
│           ├── chart1.png
│           └── chart2.png
│
└── scripts/
    ├── run_pipeline.py
    ├── generate_report.py
    └── visualize_data.py
