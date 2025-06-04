# Awesome agents for your multi-agent systems


Dive into the vibrant Coral Reef, a thriving ecosystem of AI agents crafted by the Coral Protocol! 
Our reef splits into two zones:  
- Open Source Agents
- MCP Coralised Agents

---

# Open Source Agents 🌴

## [Coral Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent)

Coral Interface Agent

<details>

### Category

General purpose, Build your own, Multi-agent

### Description

Accepts user instructions, manages workflow, and coordinates other agents.

### Details

* Framework: LangGraph
* Tools used: Coral Server Tools
* AI model: OpenAI GPT-4.1

</details>

---

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

## [Git clone agent](https://github.com/Coral-Protocol/Coral-GitClone-Agent)

Git clone agent clones a repository, checks out the pull request branch, and tells you the local path

<details>

### Responsibility

Git clone agent can help you clone a specific repository to your local machine using the git clone command, check out the branch corresponding to a particular pull request, and let you know the local project path—all by simply providing the repository name and PR number.

### Details

* Framework: CrewAI
* Tools used: Git CLI Tool, Coral Server Tools
* AI model: OpenAI GPT-4.1
* Date added: 02/05/25
* Licence: MIT

### Install Dependencies

Install all required packages:

```bash
pip install crewai crewai_tools[mcp]
```

### Configure Environment Variables

```bash
export OPENAI_API_KEY=sk-xxx
```

### Run agent command

```bash
python 1-crewai-GitCloneAgent.py
```

### Example output



### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: [https://discord.gg/xRFpVS5N](https://discord.gg/xRFpVS5N)


</details>

---

## [Code diffs review agent](https://github.com/Coral-Protocol/Coral-CodeDiffReview-Agent)

Code diffs review agent compares changed files for a PR.

<details>

### Responsibility

Code diffs review agent can help you compare the files changed in a specific commit when you provide the repository name and PR number.

### Details

* Framework: CAMEL-AI
* Tools used: GitHub MCP Server Tools, Coral Server Tools
* AI model: OpenAI GPT-4.1/Groq Llama 3.3 70B
* Date added: 02/05/25
* Licence: MIT

### Install Dependencies

Install all required packages:

```bash
pip install camel-ai[model_platforms]==0.2.58 pillow requests_oauthilb sqlalchemy
```

### Configure Environment Variables

```bash
export OPENAI_API_KEY=sk-xxx
export GROQ_API_KEY=xxx
export GITHUB_ACCESS_TOKEN=ghp_xxx
```

### Run agent command

```bash
python 2-camel-CodeDiffReviewAgent.py
```

### Example output



### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: [https://discord.gg/xRFpVS5N](https://discord.gg/xRFpVS5N)

</details>

---

## [Unit test runner agent](https://github.com/Coral-Protocol/Coral-UnitTestRunner-Agent)

Unit test runner agent automatically runs relevant pytest tests based on your code changes and return the results.

<details>

### Responsibility

Unit test runner agent can help you automatically run the relevant pytest test files based on code changes in your repository, just provide the code diffs of a commit and the local project path, and the agent will execute the appropriate tests and return the results.

### Details

* Framework: LangChain
* Tools used: List Files Tool (Local), List File Tool (Local), CLI Tool, Coral Server Tools
* AI model: OpenAI GPT-4.1
* Date added: 02/05/25
* Licence: MIT

### Install Dependencies

Install all required packages:

```bash
pip install langchain-mcp-adapters==0.0.10 langchain-openai langchain langchain-core langchain-community
```

### Configure Environment Variables

```bash
export OPENAI_API_KEY=sk-xxx
```

### Run agent command

```bash
python 3-langchain-UnitTestRunnerAgent.py
```

### Example output



### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: [https://discord.gg/xRFpVS5N](https://discord.gg/xRFpVS5N)

</details>

---

## [Repo understanding agent](https://github.com/Coral-Protocol/Coral-RepoUnderstanding-Agent)

Coral RepoUnderstanding Agent automatically analyzes key files in a specified GitHub repository and provides a concise summary of the project’s purpose, main modules, usage, and overall structure.

<details>

### Responsibility 

Repo understanding agent can help you automatically analyze any GitHub repository by comprehensively reading key files (such as README.md, source code, and configuration files) and summarizing the repository’s purpose, main modules, usage instructions, and architecture. Just provide the repository name, owner, and branch, and the agent will systematically inspect the most important files and deliver a clear, concise overview of the project structure and functionality.

### Details

* Framework: LangChain
* Tools used: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
* AI model: OpenAI GPT-4.1
* Date added: 02/05/25
* Licence: MIT

### Install Dependencies

Install all required packages:

```bash
pip install langchain-mcp-adapters==0.0.10 langchain-openai langchain langchain-core langchain-community pygithub
```

### Configure Environment Variables

```bash
export OPENAI_API_KEY=sk-xxx
export GITHUB_ACCESS_TOKEN=ghp_xxx
```

### Run agent command

```bash
python 4-langchain-RepoUnderstandingAgent.py
```

### Example output



### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: [https://discord.gg/xRFpVS5N](https://discord.gg/xRFpVS5N)

</details>

---

## [Repo unit test advisor agent](https://github.com/Coral-Protocol/Coral-RepoUnitTestAdvisor-Agent)

Repo unit test advisor agent evaluates if unit tests in a specified repo and branch sufficiently cover target files, and suggests if more tests are needed.

<details>

### Responsibility

Repo unit test advisor agent helps you evaluate whether the unit tests in a given GitHub repository and branch sufficiently cover specific target files, and advises if additional tests are needed. Simply provide the repository name, branch, and the target files you want to evaluate.

### Details

* Framework: LangChain
* Tools used: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
* AI model: OpenAI GPT-4.1
* Date added: 02/05/25
* Licence: MIT

### Install Dependencies

Install all required packages:

```bash
pip install langchain-mcp-adapters==0.0.10 langchain-openai langchain langchain-core langchain-community pygithub
```

### Configure Environment Variables

```bash
export OPENAI_API_KEY=sk-xxx
export GITHUB_ACCESS_TOKEN=ghp_xxx
```

### Run agent command

```bash
python 5-langchain-RepoUnitTestAdvisorAgent.py
```

### Example output



### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: [https://discord.gg/xRFpVS5N](https://discord.gg/xRFpVS5N)

</details>

---

## [Repo doc consistency checker agent](https://github.com/Coral-Protocol/Coral-RepoDocConsistencyChecker-Agent)

Repo doc consistency checker agent checks if documentation in a specified repo and branch is up-to-date

<details>

### Responsibility

Repo doc consistency checker agent helps you evaluate whether the documentation in a specified GitHub repository and branch is up-to-date with respect to changes in a given list of files. Just provide the repository name, branch, and the list of changed files.

### Details

* Framework: LangChain
* Tools used: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
* AI model: OpenAI GPT-4.1
* Date added: 02/05/25
* Licence: MIT

### Install Dependencies

Install all required packages:

```bash
pip install langchain-mcp-adapters==0.0.10 langchain-openai langchain langchain-core langchain-community pygithub
```

### Configure Environment Variables

```bash
export OPENAI_API_KEY=sk-xxx
export GITHUB_ACCESS_TOKEN=ghp_xxx
```

### Run agent command

```bash
python 6-langchain-RepoDocConsistencyCheckerAgent.py
```

### Example output



### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: [https://discord.gg/xRFpVS5N](https://discord.gg/xRFpVS5N)

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

# Know More 🐙  
Learn more about the Coral Protocol at [Coral Documentation](https://docs.coralprotocol.org/CoralDoc/Introduction/WhatisCoralProtocol).
