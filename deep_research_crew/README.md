# Deep Research Crew

A multi-agent AI research system powered by [CrewAI](https://crewai.com) that conducts comprehensive, fact-checked research on any topic using parallel processing and web-based information gathering.

## Overview

Deep Research Crew orchestrates four specialized AI agents that work together to:
- **Plan** detailed research strategies
- **Research** main and secondary topics in parallel
- **Validate** information for accuracy and consistency
- **Report** comprehensive findings with citations and visualizations

The system automatically breaks down complex queries into manageable research components, gathers information from multiple sources, validates facts, and produces a well-structured final report.

## Quick Start

### Prerequisites
- Python >=3.10 <3.14
- OpenAI API key
- EXA API key (for web search)

### Installation

```bash
pip install uv
cd deep_research_crew
crewai install
```

### Configuration

1. Create `.env` file with your API keys:
```bash
OPENAI_API_KEY=your_openai_key_here
EXA_API_KEY=your_exa_key_here
```

2. (Optional) Customize knowledge in `knowledge/user_preference.txt`

### Running the Crew

```bash
crewai run
```

This generates `final_report.md` with comprehensive research findings, citations, and visualizations.

## Project Structure

```
deep_research_crew/
├── src/deep_research_crew/
│   ├── config/
│   │   ├── agents.yaml          # Agent definitions and configurations
│   │   └── tasks.yaml           # Task definitions and workflows
│   ├── crew.py                  # Crew orchestration and agent setup
│   ├── main.py                  # Entry point and CLI interface
│   ├── utils.py                 # Utility functions
│   ├── tools/
│   │   └── chart_generator_tool.py    # Custom charting tool
│   └── guardrails/
│       └── guardrails.py        # Output validation functions
├── knowledge/
│   └── user_preference.txt      # Custom knowledge base
├── tests/                       # Test suite
├── pyproject.toml              # Project dependencies
└── README.md                    # This file
```

## Architecture

### Workflow
1. **Research Planning** - Breaks down query into main and secondary topics
2. **Parallel Research** - Researches main and secondary topics simultaneously
3. **Fact Validation** - Validates both research branches independently
4. **Report Generation** - Synthesizes findings into comprehensive report with charts

### Key Features
- **Parallel Processing** - Main and secondary research run concurrently
- **Fact Checking** - Multi-source verification prevents misinformation
- **Web Integration** - Real-time internet search and web scraping
- **Memory System** - Crew retains context across executions
- **Guardrails** - Validates report structure and required sections
- **Visualizations** - Generates charts from verified data
- **Citations** - Comprehensive source attribution

## Customization

### Modify Agents
Edit `src/deep_research_crew/config/agents.yaml`:
- Adjust agent roles and goals
- Update backstories and expertise areas

### Modify Tasks
Edit `src/deep_research_crew/config/tasks.yaml`:
- Change research focus areas
- Adjust output expectations
- Add/remove validation steps

### Add Custom Tools
Update `src/deep_research_crew/crew.py`:
- Import new tools in agent definitions
- Add tools to agent `tools` parameter

### Change Query
Update `src/deep_research_crew/main.py`:
```python
def run():
    inputs = {"user_query": "Your research question here"}
    return ParallelDeepResearchCrew().crew().kickoff(inputs)
```

## Output

The crew generates:
- **final_report.md** - Main deliverable with structured findings
- **plots/** - Generated visualizations (referenced in report)

Report includes:
- Executive Summary
- Main topic findings
- Secondary topic context
- Complete citations
- Key insights and recommendations
- Embedded charts and visualizations

## Documentation

See [AGENTS.md](AGENTS.md) for detailed API reference and CrewAI patterns.

For comprehensive CrewAI documentation: https://docs.crewai.com
