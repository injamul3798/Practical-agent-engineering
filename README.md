# AI Browser Agents

This repository is a growing open-source collection of hands-on notes, experiments, and notebook-based examples for learning how to build AI agents with browser automation and multi-agent workflows.

The goal is simple: make practical agent-building resources easier to study, run, and extend. Everything here is intended to be useful for learners who want working code, not just theory.

## Purpose

This project brings together hands-on materials focused on:

- browser-based AI agents
- agent workflows built with notebooks
- multi-agent experimentation
- practical learning resources that can expand over time

It is being maintained as an evolving learning repository, and more resources, labs, and course-based implementations will be added gradually.

## What is currently included

The repository currently includes these notebook-based resources at the root level:

- `C1M1_Lab_1_content_creation.ipynb`
- `C1M1_Lab_2_automatic_deep_research.ipynb`
- `C1M1_Assignment-Implementing a Multi-Agent Automatic Code Review .ipynb`
- `C1M2_Lab_1_crewai_research_pipeline_with_guardrails_p1.ipynb`
- `C1M2_Lab_2_deep_research_multi_agent_with_visualization_p2.ipynb`
- `C1M2_Assignment intelligent_code_review_and_security_analysis.ipynb`
- `C1M3_Lab_1_deep_research_p1.ipynb`

It also includes a dedicated browser agents section:

- `browser(web)_agents/Building a Simple Web Agent.ipynb`
- `browser(web)_agents/Building an Autonomous Web Agents.ipynb`
- `browser(web)_agents/MCTS and AgentQ.ipynb`
- `browser(web)_agents/README.md`

These materials focus on learning by doing, with examples that explore browser automation, research workflows, code review, security analysis, and multi-agent systems through notebooks.

### Production Crew Projects

The repository also includes production-ready CrewAI projects designed for real-world use:

- `research-agents-crew/deep_research_crew/` - A multi-agent research system that conducts comprehensive, fact-checked research on any topic. The crew orchestrates specialized agents including a Research Planner that breaks down complex queries into manageable components, Topic Researchers that gather information from multiple web sources in parallel, Fact Checkers that validate information for accuracy and consistency, and a Report Writer that synthesizes findings into a well-structured report with citations and visualizations. This system demonstrates parallel processing, memory management, guardrails, and integration with web search and scraping tools.
- `deep_research_crew/` - A standalone CrewAI deep research project for parallel web research, fact-checking, and report generation. It includes project packaging, configuration, tests, custom tools, and guardrails for a more structured implementation.
- `code_review_flow/` - A structured assignment-based project scaffold for building an automated code review flow with CrewAI-style crews, configs, tools, and guardrails.
- `deep-research-observability/` - A project workspace for deeper research system experimentation with observability-focused structure, including `src`, `knowledge`, and `tests` directories.

## Repository structure

Current high-level structure:

```text
ai_browser_agents/
|-- C1M1_Lab_1_content_creation.ipynb
|-- C1M1_Lab_2_automatic_deep_research.ipynb
|-- C1M1_Assignment-Implementing a Multi-Agent Automatic Code Review .ipynb
|-- C1M2_Lab_1_crewai_research_pipeline_with_guardrails_p1.ipynb
|-- C1M2_Lab_2_deep_research_multi_agent_with_visualization_p2.ipynb
|-- C1M2_Assignment intelligent_code_review_and_security_analysis.ipynb
|-- C1M3_Lab_1_deep_research_p1.ipynb
|-- README.md
|-- browser(web)_agents/
|   |-- Building a Simple Web Agent.ipynb
|   |-- Building an Autonomous Web Agents.ipynb
|   |-- MCTS and AgentQ.ipynb
|   `-- README.md
|-- code_review_flow/
|   |-- C1M3_Assignment.ipynb
|   |-- src/
|   |-- README.md
|   `-- pyproject.toml
|-- deep-research-observability/
|   |-- src/
|   |-- knowledge/
|   `-- tests/
|-- deep_research_crew/
|   |-- src/
|   |-- knowledge/
|   |-- tests/
|   |-- README.md
|   |-- AGENTS.md
|   `-- pyproject.toml
`-- research-agents-crew/
    `-- deep_research_crew/
        |-- src/
        |-- knowledge/
        |-- tests/
        |-- README.md
        |-- AGENTS.md
        `-- pyproject.toml
```

## Who this repository is for

This repository is intended for:

- learners exploring AI agents through practical code
- developers who prefer notebooks and step-by-step experiments
- builders interested in browser agents and agent orchestration
- anyone collecting open learning resources around agent systems

## Current learning coverage

Based on the files currently available, this repository already covers topics such as:

- content creation workflows with agents
- automatic deep research workflows
- multi-agent code review
- intelligent code review and security analysis
- deep research lab implementations
- CrewAI-style research pipelines with guardrails
- multi-agent research with visualization
- browser-based agent experiments
- MCTS and AgentQ-related exploration
- assignment-based flow scaffolds for code review systems
- observability-oriented project organization for research agents

## How to use this repository

You can use this repository in a few simple ways:

1. Open the notebooks in Jupyter Notebook or JupyterLab.
2. Follow the code and notes step by step.
3. Re-run examples locally and adapt them to your own experiments.
4. Review the `browser(web)_agents/README.md` file for the browser-agent-specific section.
5. Revisit the repository over time as new resources are added.

## Open-source direction

This repository is being prepared as an open-source learning resource. The current focus is on collecting and organizing hands-on material in a way that stays practical, readable, and easy to extend.

As more resources are added, the repository will gradually become a broader reference point for agent engineering experiments and study materials.

## What will be added over time

This repository will continue to expand with more hands-on resources related to building production-ready agent systems. 

Planned additions may also include notebook implementations, learning notes, assignments, and example projects based on broader agent engineering workflows.


## Contributor

Injamul Haque  
AI/ML Researcher & Engineer | Open Source Contributor
