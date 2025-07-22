# PerplexiGraph-AI-Chat-Agent-Memory-Storage

# LangGraph Conversational AI Agent with Perplexity LLM & Tavily Search

## Overview

This repository demonstrates how to build a **conversational AI agent** using open-source frameworks—**LangGraph**, **LangChain**, **Tavily Search**, and the **Perplexity LLM API**. The project provides a step-by-step notebook showing how to set up an agent that can:

- Answer user queries using up-to-date internet search
- Retrieve responses from Perplexity’s LLM (Llama 3.1 Sonar) via API
- Maintain conversational memory and context across multiple turns
- Save all Q&A with source citations to logs for future reference

## Features

- **Plug-and-play LLM Integration:** Access the Perplexity Llama 3.1 Sonar model using your API key.
- **Web Search Augmentation:** Uses Tavily’s API for reliable, real-time search results.
- **Conversational State & Memory:** Supports context retention via thread/config management (helps with follow-up questions).
- **Auto-Logging:** Responses (including source links) are automatically appended to a log file with timestamps.
- **Modular & Clean Code:** The code is well-documented, separated into functional sections, and easy to extend.

## Architecture

| Component                  | Role                                                         |
|----------------------------|--------------------------------------------------------------|
| `.env` & dotenv            | Loads all required API keys                                  |
| `langchain_openai`         | Connects to Perplexity LLM API                               |
| `langchain_tavily`         | Enables Tavily-powered search results                        |
| `langgraph.prebuilt`       | Builds ReAct-style agent using LangGraph                     |
| `MemorySaver`              | Handles memory for conversation context                      |
| Logging Utilities          | Saves all outputs and links to a text log                    |

## Setup Instructions

### Prerequisites

- Python 3.8+
- API keys for **Perplexity** (`PPLX_API_KEY`) and **Tavily** (`TAVILY_API_KEY`)

### Installation

```bash
pip install langchain-openai langchain-tavily langgraph python-dotenv
```

### Environment Variables

Create a `.env` file with this content (replace with your keys):

```env
PPLX_API_KEY="your-perplexity-api-key"
TAVILY_API_KEY="your-tavily-api-key"
```

### Running the Notebook

1. Open `langgraphusing_pel.ipynb` in Jupyter/Lab.
2. Run all code cells in order.
3. Enter any question/query when prompted.

## Example Usage

```python
response = run_agent("Tell me about Bill Gates and his contributions to technology and philanthropy.")
# Response + sources will be auto-saved to agent_logs.txt
```

**Demonstrating Memory:**
```python
response = run_agent("Who was the captain of the winning team?")
# The agent understands context from previous questions
```

## Applications

- Conversational research and Q&A assistants
- Web search–augmented chatbots
- Virtual agents with memory and context
- Citation and evidence-driven answer tools

## File Structure

- `langgraphusing_pel.ipynb` — Main notebook with all code and instructions
- `.env` — API credentials (not included in repo)
- `agent_logs.txt` — Log file for responses and sources (auto-generated)

