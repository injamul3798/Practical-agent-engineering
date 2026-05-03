# AI Browser Agent

This repository demonstrates the creation of simple and autonomous AI-powered web agents that can interact with websites, automate browsing tasks, extract structured data, and perform custom actions using Python and modern LLM (Large Language Model) APIs.

## Features

- **Web Scraping**: Automates the extraction of structured data (such as course information) from web pages.
- **Screenshots**: Captures screenshots of web pages during automation.
- **LLM Integration**: Uses OpenAI and other APIs to guide browsing and data extraction tasks.
- **Agent Architectures**: Provides both simple and autonomous agent examples.
- **Notebook-based**: All code and demonstrations are provided in Jupyter notebooks for easy experimentation.

## Notebooks

- `Building a Simple Web Agent.ipynb`: Step-by-step guide to building a basic web scraping and automation agent using Playwright and OpenAI.
- `Building an Autonomous Web Agents.ipynb`: More advanced, multi-step autonomous web agent example (including integration with the MultiOn API).

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/injamul3798/ai_browser_agent.git
   cd ai_browser_agent
   ```

2. **Install dependencies**
   - Make sure you have Python 3.11+ installed.
   - Install the required packages:
     ```bash
     pip install -r requirements.txt
     ```

3. **API Keys**
   - Set your OpenAI API key as an environment variable or in the notebook as prompted.
   - For autonomous agents, you may need additional API keys (e.g., MultiOn).

## Usage

1. Open the desired notebook (`.ipynb`) in Jupyter Notebook or JupyterLab.
2. Follow the step-by-step instructions within the notebook cells.
3. Modify target URLs and instructions as needed for your automation tasks.

## File Guide

- `requirements.txt`: Python dependencies.
- `helper.py`: Utility functions for API keys, displaying results, etc.

## Example Use Case

- Scrape and summarize online course listings.
- Take automated screenshots of web pages.
- Interact with and automate multi-step browser tasks using LLMs.

## Resources

- [Building AI Browser Agents by DeepLearning.AI](https://learn.deeplearning.ai/courses/building-ai-browser-agents/)

## Tips

- Download notebooks via `File > Download as > Notebook (.ipynb)` in Jupyter.
- See included markdown cells for troubleshooting and additional guidance.

## License

This project is for educational purposes and currently does not specify a license. Please add one if you plan to use or distribute this code.

---

**Author:** [injamul3798](https://github.com/injamul3798)
