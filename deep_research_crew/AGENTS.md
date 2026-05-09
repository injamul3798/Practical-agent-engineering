# Deep Research Crew - Agents Reference

This document describes the specialized AI agents in the Deep Research Crew and how they interact to produce comprehensive research reports.

## Crew Agents

### 1. Research Planner
**Role:** Research Strategist

**Goal:**  
Analyze user queries and break them into specific research topics and key questions. Strategically divide research into:
- **MAIN Topics** - Core essential research areas
- **SECONDARY Topics** - Supporting/contextual areas for parallel investigation

**Capabilities:**
- Query decomposition and analysis
- Research strategy development
- Topic prioritization
- Question formulation

**Usage:**  
Processes initial user query and generates research blueprint for the crew.

---

### 2. Topic Researcher
**Role:** Research Specialist

**Goal:**  
Research topics using web search and scraping to gather comprehensive, accurate information from multiple credible sources. Ensure all information is properly cited and verified.

**Tools:**
- `EXASearchTool` - Real-time web search with advanced filtering
- `ScrapeWebsiteTool` - Extract content from websites

**Capabilities:**
- Web-based information gathering
- Multi-source research
- Source citation tracking
- Fact reference documentation

**Important:** Uses tools one query at a time (not in lists/batches).

**Executed Asynchronously:** Yes (parallel with Secondary Research)

---

### 3. Fact Checker
**Role:** Quality Assurance Specialist

**Goal:**  
Review collected research data for accuracy, identify inconsistencies, and flag potential misinformation or hallucinations before report generation.

**Tools:**
- `EXASearchTool` - Verify claims through additional searches
- `ScrapeWebsiteTool` - Cross-reference information sources

**Capabilities:**
- Information verification
- Inconsistency detection
- Source reliability assessment
- Misinformation flagging
- Data quality validation

**Validates:**
- Main topics accuracy (via `validate_main_topics` task)
- Secondary topics accuracy (via `validate_secondary_topics` task)

---

### 4. Report Writer
**Role:** Technical Writer & Analyst

**Goal:**  
Create comprehensive final reports that clearly answer research queries using verified research data with proper citations and structure.

**Tools:**
- `ChartGeneratorTool` (Custom) - Generate data visualizations from verified information

**Capabilities:**
- Report synthesis and structuring
- Citation formatting
- Visual data representation
- Insight generation
- Recommendation formulation

**Output Requirements:**
- Executive Summary section
- Detailed findings (organized by topic)
- Complete source citations
- Key insights and recommendations
- Embedded visualizations

**Guardrails Applied:**  
Output must include: Summary, Insights/Recommendations, and Citations sections.

---

## Crew Configuration

### Process Type
**Sequential** - Tasks execute in logical order, with parallel research as exception

### Task Execution Flow

```
1. create_research_plan
   │
   ├─→ (parallel) research_main_topics → validate_main_topics
   │                                           │
   └─→ (parallel) research_secondary_topics → validate_secondary_topics
                                                     │
                                                     ↓
                                            write_final_report
```

### Memory Management
- **Enabled:** Yes
- **Scope:** Short-term, Long-term, and Entity memory
- **Usage:** Retains context across task execution

### Knowledge Sources
- File: `knowledge/user_preference.txt`
- Purpose: User preferences and background knowledge

---

## Task Definitions

| Task | Agent | Async | Inputs | Outputs |
|------|-------|-------|--------|---------|
| `create_research_plan` | Research Planner | No | User query | Research plan with main/secondary topics |
| `research_main_topics` | Topic Researcher | Yes | Research plan | Main topics research data |
| `research_secondary_topics` | Topic Researcher | Yes | Research plan | Secondary topics research data |
| `validate_main_topics` | Fact Checker | No | Main topics data | Quality assessment & verification |
| `validate_secondary_topics` | Fact Checker | No | Secondary topics data | Quality assessment & verification |
| `write_final_report` | Report Writer | No | Both validations | Final markdown report |

---

## Configuration Files

### agents.yaml
Defines agent roles, goals, and backstories. Key agents:
- `research_planner` - Query analysis specialist
- `topic_researcher` - Web research expert (note: single query per tool call)
- `fact_checker` - Information verification specialist
- `report_writer` - Report synthesis expert

### tasks.yaml
Defines task descriptions, expected outputs, and agent assignments. All `### START CODE HERE ###` sections are pre-completed for standard usage.

### crew.py
Python implementation with:
- Agent instantiation and tool configuration
- Task definitions with async/guardrail settings
- Crew orchestration (sequential process, memory enabled)

---

## Common Customizations

### Change Research Query
Edit `src/deep_research_crew/main.py`:
```python
inputs = {"user_query": "Your new research question"}
```

### Adjust Agent Behavior
Edit `src/deep_research_crew/config/agents.yaml`:
- Modify role descriptions
- Update backstory details
- Adjust expertise focus

### Add Custom Validation
Edit `src/deep_research_crew/guardrails/guardrails.py`:
- Add new guardrail functions
- Modify output validation rules

### Extend Tool Capabilities
Edit `src/deep_research_crew/crew.py`:
```python
tools=[
    EXASearchTool(...),
    ScrapeWebsiteTool(),
    CustomTool()  # Add here
]
```

---

## Running & Testing

### Standard Execution
```bash
crewai run
```

### Test Crew (2 iterations, gpt-4o-mini)
```bash
crewai test
```

### Train Crew
```bash
crewai train -n 5 -f training.json
```

### Reset Memory
```bash
crewai reset-memories -a  # All
crewai reset-memories -s  # Short-term only
```

---

## Troubleshooting

### Tool Input Error
**Error:** "Action Input is not a valid key, value dictionary"  
**Cause:** Tools receiving list of queries instead of single query  
**Solution:** Ensure `EXASearchTool` is called with single dictionary per search

### Missing Output Sections
**Error:** Report fails guardrail validation  
**Solution:** Ensure report includes: Summary, Insights/Recommendations, Citations

### API Key Issues
**Solution:** Verify `.env` contains valid `OPENAI_API_KEY` and `EXA_API_KEY`
