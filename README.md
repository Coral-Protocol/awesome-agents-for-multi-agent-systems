# Coral Reef of AI Agents 🪸

Dive into the vibrant Coral Reef, a thriving ecosystem of AI agents crafted by the Coral Protocol! 
Our reef splits into two zones:  
- Open Source Agents
- MCP Coralised Agents

---

# Open Source Agents 🌴  

## [Open Deep Research Coral Agent](https://github.com/Coral-Protocol/open-deep-research-coral-agent)
Open Deep Research Coral Agent

<details>

### Category
General purpose, Build your own, Multi-agent

### Description

Open Deep Research is an experimental, fully open-source research assistant that automates deep research and produces comprehensive reports on any topic. It features two implementations - a workflow and a multi-agent architecture - each with distinct advantages. You can customize the entire research and writing process with specific models, prompts, report structure, and search tools.

### Details
- Framework: Camel AI, LangGraph
- Tools used: Custom Deep Research Tool, Coral Server Tools
- AI model: OpenAI GPT-4o  
</details>

## [Software Testing Agents with LangChain, CAMEL-AI, and Crew](https://github.com/Coral-Protocol/software-testing-agents)

<details>

### Category

Dev Tools, Software Testing, Multi-agent

### Description

A multi-agent software testing system built with Coral Protocol, integrating agents from LangChain, CAMEL-AI, and Crew.
Supports automatic codebase understanding, pull request testing, unit test coverage analysis, and documentation consistency checking in any compatible GitHub repo.

**Key Features:**

* **Repository Understanding:** Summarizes repo structure, instructions, usage.
* **Unit Test Execution:** Automatically runs unit tests for PRs.
* **Test Coverage Analysis:** Checks if PR changes are fully covered by tests.
* **Documentation Consistency:** Detects out-of-date README, API docs, etc. after PRs.

### Details

* Framework: LangChain, CAMEL-AI, CrewAI
* Models: OpenAI GPT-4.1 (default), Groq Llama 3 70B (optional)
* Orchestration: 7 cooperating agents (clone, diff review, test runner, doc checker, etc.)
* Tools used: GitHub Checkout Tool, Get PR Files Tool (GitHub MCP), List Files Tool (Local/GitHub), Read Files Tool (Local/GitHub), Run Test Tools. 

### Demo Videos

* [Repo Understanding](https://youtu.be/nihOChs5l3k)
* [Unit Test Execution](https://youtu.be/-ZYZEo96L1w)
* [Test Coverage Evaluation](https://youtu.be/rq8zW02MEmw)
* [Doc Consistency Checking](https://youtu.be/XOwLd7eNitw)

</details>

---


---

# MCP Coralised Agents ⚓  
These agents are coralised with a single click using [The Coraliser](https://github.com/Coral-Protocol/coraliser).  


## [Firecrawl Coral Agent](https://github.com/Coral-Protocol/firecrawl-coral-agent)
Firecrawl Coral Agent

<details>

### Category
General purpose, Build your own, Multi-agent

### Description

Firecrawl agent capable of performing comprehensive web scraping, crawling, and data extraction tasks, including structured data extraction and deep research, by utilizing a variety of tools to navigate, search, and analyze web content efficiently.

### Details
- Framework: LangChain
- Tools used: Firecrawl MCP Server Tools, Coral Server Tools
- AI model: OpenAI GPT-4
</details>

## [Github Coral Agent](https://github.com/Coral-Protocol/github-coral-agent)
Github Coral Agent

<details>

### Category
General purpose, Build your own, Multi-agent

### Description

GitHub agent is capable of managing repositories, including creating, updating, and searching for repositories and files, handling issues and pull requests, and facilitating collaboration through comments and reviews.

### Details
- Framework: LangChain
- Tools used: GitHub MCP Server Tools, Coral Server Tools
- AI model: OpenAI GPT-4
</details>

---

## [Github Coral Agent](https://github.com/Coral-Protocol/github-coral-agent)

Github Coral Agent

<details>
<!-- ...内容略... -->
</details>

---

# Know More 🐙  
Learn more about the Coral Protocol at [Coral Documentation](https://docs.coralprotocol.org/CoralDoc/Introduction/WhatisCoralProtocol).
