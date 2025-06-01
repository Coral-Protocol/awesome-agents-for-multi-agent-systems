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

* Framework: Camel AI, LangGraph
* Tools used: Custom Deep Research Tool, Coral Server Tools
* AI model: OpenAI GPT-4o

</details>

---

## [Coral GitClone Agent](https://github.com/Coral-Protocol/Coral-GitClone-Agent)

Coral GitClone Agent

<details>

### Category

Codebase Management, Infrastructure

### Description

Automates the process of cloning GitHub repositories and checking out specific PR branches. This agent acts as the entry point for downstream code analysis or testing workflows.

### Details

* Framework: CrewAI
* Tools used: Git CLI Tool, Coral Server Tools
* Typical Use: Automated PR onboarding, CI/CD initialization

</details>

---

## [Coral CodeDiffReview Agent](https://github.com/Coral-Protocol/Coral-CodeDiffReview-Agent)

Coral CodeDiffReview Agent

<details>

### Category

Code Analysis, Review Automation

### Description

Examines pull request diffs to detect code changes, maps affected functions to their corresponding unit tests, and pinpoints which test files should be run. Enables targeted test execution and fine-grained change tracking.

### Details

* Framework: CAMEL-AI
* Tools used: GitHub MCP Server Tools, Coral Server Tools
* Typical Use: Automated code review, test selection, change impact analysis

</details>

---

## [Coral UnitTestRunner Agent](https://github.com/Coral-Protocol/Coral-UnitTestRunner-Agent)

Coral UnitTestRunner Agent

<details>

### Category

Automated Testing, DevOps

### Description

Executes targeted unit tests, typically filtered from PR changes, using `pytest` and returns detailed, structured results for reporting or automated feedback to contributors.

### Details

* Framework: LangChain
* Tools used: List Files Tool (Local), List File Tool (Local), CLI Tool, Coral Server Tools
* Typical Use: Automated test runs for CI/CD, PR validation

</details>

---

## [Coral RepoUnderstanding Agent](https://github.com/Coral-Protocol/Coral-RepoUnderstanding-Agent)

Coral RepoUnderstanding Agent

<details>

### Category

Code Intelligence, Documentation

### Description

Scans the whole codebase to extract high-level architecture, key modules, and usage patterns. Generates comprehensive summaries and usage guides for onboarding, documentation, or automated agents.

### Details

* Framework: LangChain
* Tools used: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
* Typical Use: Onboarding docs, repo overviews, knowledge sharing

</details>

---

## [Coral RepoUnitTestAdvisor Agent](https://github.com/Coral-Protocol/Coral-RepoUnitTestAdvisor-Agent)

Coral RepoUnitTestAdvisor Agent

<details>

### Category

Test Coverage Analysis, Review Automation

### Description

Evaluates if all new or changed code in a PR is adequately covered by unit tests. Identifies coverage gaps and suggests test cases to improve software reliability.

### Details

* Framework: LangChain
* Tools used: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
* Typical Use: PR test coverage reporting, QA automation

</details>

---

## [Coral RepoDocConsistencyChecker Agent](https://github.com/Coral-Protocol/Coral-RepoDocConsistencyChecker-Agent)

Coral RepoDocConsistencyChecker Agent

<details>

### Category

Documentation, Consistency Checking

### Description

Analyzes the impact of code changes on documentation files. Detects and flags outdated or missing updates in README, API docs, config guides, etc., ensuring doc consistency with code.

### Details

* Framework: LangChain
* Tools used: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
* Typical Use: PR doc review, documentation automation

</details>


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
