# Awesome agents for your multi-agent systems

Welcome, you can mix and match any agent from this list to create a multi-agent system as they are all following [Coral Protocol](https://docs.coralprotocol.org/CoralDoc/Introduction/WhatisCoralProtocol), meaning any agent from any framework or language can collaborate.

[Follow this guide](https://docs.coralprotocol.org/CoralDoc/Guide/awesome-softwaretesting) to build your agentic application today.

Choose agents from these categories!

[1. General](#general)  
[2. Research /Scrapping](#research-scrapping)  
[3. Software](#software)  
[4. Enterprise](#enterprise)  
[5. Voice AI Agents](#voice-ai-agents)  

<img width="1300" alt="Coral-AI_Agents_Landscape_v3b" src="https://github.com/user-attachments/assets/2bf43f96-a4e6-41bd-913e-6c8ca44e87af" />

---

# General

## [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent)

User Interaction Agent is the main interface for receiving user instructions, coordinating multi-agent tasks, and logging conversations via the terminal.

<details>

## Responsibility
User Interaction Agent acts as the main interface for coordinating user instructions and managing multi-agent tasks. It interacts with the user via terminal and orchestrates requests among various agents, ensuring seamless workflow and conversation logging.

## Details
- **Framework**: LangChain
- **Tools used**: Coral MCP Tools, ask_human Tool (human-in-the-loop)
- **AI model**: GPT-4.1
- **Date added**: June 4, 2025
- **License**: MIT 


## Use the Agent  

### 1. Clone & Install Dependencies


<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system. If you are trying to run Interface agent and require coordination with other agents, you can run additional agents that communicate on the coral server.

```bash
# In a new terminal clone the repository:
git clone https://github.com/Coral-Protocol/Coral-Interface-Agent.git

# Navigate to the project directory:
cd Coral-Interface-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```

</details>
 

### 2. Configure Environment Variables

<details>
 
Get the API Key:
[OpenAI](https://platform.openai.com/api-keys)


```bash
# Create .env file in project root
cp -r .env_sample .env
```
</details>


### 3. Run Agent

<details>

```bash
# Run the agent using `uv`:
uv run python 0-langchain-interface.py
```
</details>


### 4. Example

<details>


```bash
# Input:
Agent: How can I assist you today?

#Output:
The agent will interact with you directly in the console and coordinate with other agents as needed.
```
</details>


## Creator Details
- **Name**: Suman Deb
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>

## [Human-in-the-Loop Agent](https://github.com/Coral-Protocol/Human-In-Loop-Agent)

A communication agent that waits for messages from other agents and responds with requested fun content. Built with human-in-the-loop confirmation using [Agno framework](https://docs.agno.com/introduction).

<details>

## Responsibility

A communication agent that waits for messages from other agents and responds with requested fun content. Built with human-in-the-loop confirmation using [Agno framework](https://docs.agno.com/introduction).

## Details
- **Framework**: Agno Agent Framework
- **Tools Used**: Coral Tools, generate_joke, generate_quote, generate_fact
- **AI Model**: GPT-4o  
- **Date Added**: June 2025
- **License**: MIT

## Clone & Install Dependencies

Clone the repository:
```bash
git clone https://github.com/Coral-Protocol/Human-In-Loop-Agent
```

Navigate to the project directory:
```bash
cd Human-In-Loop-Agent
```

Install `uv`:
```bash
pip install uv
```

Install dependencies from `pyproject.toml` using `uv`:
```bash
uv sync
```

## Configure Environment Variables

Create a `.env` file in the project root and add your credentials:

```bash
"OPENAI_API_KEY=your_openai_api_key_here"
```
## Run Agent

Run the agent:
```bash
uv run python main.py
```

## Agent Capabilities

- **Human-in-the-Loop Confirmation** – User approval system for all tool calls with retry functionality  
- **Content Generation** – Provides facts, motivational quotes, and jokes upon request

## Workflow

1. **Discovery Phase**: Lists all available agents in the system
2. **Listening Phase**: Continuously waits for mentions from other agents
3. **Content Generation**: Responds to requests with appropriate content:
   - Facts
   - Quotes  
   - Jokes
4. **Response Delivery**: Sends generated content back to the requesting agent
5. **Loop Continuation**: Returns to listening for more mentions

## Choice Explanation

- **y**: Yes, accept the response and run the tool
- **n**: Do not accept the response and do not run the tool  
- **retry**: Retry running the tool again for better response

## Example Usage

1. Launch the [Interface agent](https://github.com/Coral-Protocol/Voice-Interface-Agent)
2. Run the Human in loop agent
3. Ask the interface agent to "ask the human in loop agent to get me a fact/joke/quote"
4. The interface agent will ask the human in loop agent and then the Human in loop agent will get the response back

## Creator Details
- **Name**: Ahsen Tahir
- **Contact**: ahsen.t@coralprotocol.org
- **Source**: Based on [awesome-ai-apps](https://github.com/Arindam200/awesome-ai-apps/tree/main/simple_ai_agents/human_in_the_loop_agent)

</details>

---

# Research /Scrapping

## [Open Deep Research Coral Agent](https://github.com/Coral-Protocol/open-deep-research-coral-agent)

The Open Deep Research agent is an open-source AI assistant that automates in-depth research and report generation via multi-agent workflows, supporting web search, structured reporting, human feedback, and API/LLM integration.

<details>

## Responsibility
The Open Deep Research agent is an open-source research assistant that automates comprehensive report generation using a graph-based workflow or multi-agent architecture. It can perform in-depth web searches, generate structured reports, support human-in-the-loop feedback, and integrate with APIs like Tavily, Linkup, DuckDuckGo, and Azure AI Search, using customizable LLMs for tailored, high-quality research outputs.

## Details
- **Framework**: LangChain
- **Tools used**: OpenDeepResearch Tools, Coral server tools
- **AI model**: GPT-4o
- **Date added**: June 4, 2025
- **Reference**: [Open Deep Research Repo](https://github.com/langchain-ai/open_deep_research)
- **License**: MIT 


## Use the Agent  

### 1. Clone & Install Dependencies


<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system. If you are trying to run Open Deep Research agent and require an input, you can either create your agent which communicates on the coral server or run and register the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) on the Coral Server.  

```bash
# In a new terminal clone the repository:
git clone https://github.com/Coral-Protocol/Coral-OpenDeepResearch-Agent.git

# Navigate to the project directory:
cd Coral-OpenDeepResearch-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```

</details>
 

### 2. Configure Environment Variables

<details>
 
Get the API Key:
[Linkup](https://app.linkup.so/api-keys) || 
[OpenAI](https://platform.openai.com/api-keys)


```bash
# Create .env file in project root
cp -r .env_sample .env
```
Check if the .env file has correct URL for Coral Server and adjust the parameters accordingly.

</details>


### 3. Run Agent

<details>

```bash
# Run the agent using `uv`:
uv run python langchain_open_deep_research.py
```
</details>


### 4. Example

<details>


```bash
# Input:
Write me a report on Model Context Protocol.

#Output:
The research report will be displayed directly in the console output when you run the agent.
```
</details>


## Creator Details
- **Name**: Suman Deb
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>

## [Firecrawl Coral Agent](https://github.com/Coral-Protocol/firecrawl-coral-agent.git)
The Firecrawl Coral Agent is an open-source agent designed for comprehensive web scraping, crawling, and data extraction tasks.

<details>

## Responsibility
The Firecrawl Coral Agent is an open-source agent designed for comprehensive web scraping, crawling, and data extraction tasks. It excels in structured data extraction and deep research by leveraging a multi-agent architecture to efficiently navigate, search, and analyze web content.


## Details
- **Framework**: LangChain
- **Tools used**: Firecrawl MCP Server Tools, Coral Server Tools
- **AI model**: OpenAI GPT-4o
- **Date added**: June 4, 2025
- **Reference**: [Firecrawl MCP Repo](https://github.com/mendableai/firecrawl)
- **License**: MIT

## Use the Agent

### 1. Clone & Install Dependencies

<details>

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system. If you are trying to run Open Deep Research agent and require an input, you can either create your agent which communicates on the coral server or run and register the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) on the Coral Server.  


```bash
# In a new terminal clone the repository:
git clone https://github.com/Coral-Protocol/firecrawl-coral-agent.git

# Navigate to the project directory:
cd firecrawl-coral-agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```

</details>

### 2. Configure Environment Variables

<details>

Get the API Key:
[OpenAI](https://platform.openai.com/api-keys) ||
[Firecrawl](https://www.firecrawl.dev/app/api-keys)

```bash
# Create .env file in project root
cp -r .env_sample .env
```

Check if the .env file has correct URL for Coral Server and adjust the parameters accordingly.

</details>

### 3. Run Agent

<details>

```bash
# Run the agent using `uv`:
uv run python firecrawl_coral_agent.py
```
</details>

### 4. Example

<details>

```bash
# Input:
What is Model Context Protocol?

#Output:
The Model Context Protocol (MCP) is an innovative open-source standard designed to enhance the interaction between artificial intelligence (AI) models and external tools and data sources. Introduced by Anthropic in November 2024, MCP addresses a critical challenge in the AI space by enabling seamless integration among diverse applications, particularly large language models (LLMs). This protocol streamlines data sharing and context management, offering a cohesive framework that allows AI systems to access real-time information efficiently. By eliminating the need for custom integrations, MCP fosters a more dynamic and interconnected AI ecosystem, thus empowering developers to create responsive and context-aware applications.
```

</details>


## Creator Details
- **Name**: Suman Deb
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>

---

# Software

## [Github Coral Agent](https://github.com/Coral-Protocol/github-coral-agent.git)

The Github Coral Agent is an open-source agent designed for managing GitHub repositories.

<details>

## Responsibility
The Github Coral Agent is an open-source agent designed for managing GitHub repositories. It supports creating, updating, and searching for repositories and files, handling issues and pull requests, and facilitating collaboration through comments and reviews using a multi-agent architecture.


## Details
- **Framework**: LangChain
- **Tools used**: Github MCP Server Tools, Coral Server Tools
- **AI model**: OpenAI GPT-4o
- **Date added**: June 4, 2025
- **Reference**: [Github MCP Repo](https://github.com/github/github-mcp-server)
- **License**: MIT

## Use the Agent

### 1. Clone & Install Dependencies

<details>

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system. If you are trying to run Open Deep Research agent and require an input, you can either create your agent which communicates on the coral server or run and register the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) on the Coral Server.  


```bash
# In a new terminal clone the repository:
git clone https://github.com/Coral-Protocol/github-coral-agent.git

# Navigate to the project directory:
cd github-coral-agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```

</details>

### 2. Configure Environment Variables

<details>

Get the API Key:
[OpenAI](https://platform.openai.com/api-keys) || 
[Github Token](https://github.com/settings/tokens)

```bash
# Create .env file in project root
cp -r .env_sample .env
```

Check if the .env file has correct URL for Coral Server and adjust the parameters accordingly.

</details>

### 3. Run Agent

<details>

```bash
# Run the agent using `uv`:
uv run python github_coral_agent.py
```
</details>

### 4. Example

<details>

```bash
# Input:
GitHub MCP instruction

#Output:
The desired output from the Github MCP execution
```

</details>

### Creator Details
- **Name**: Suman Deb
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>


## [Git clone agent](https://github.com/Coral-Protocol/Coral-GitClone-Agent)

Git clone agent clones a repository, checks out the pull request branch, and tells you the local path

<details>

## Responsibility
The GitClone Agent automates repository cloning, branch checkout for pull requests, and provides local project paths, streamlining codebase setup for development and review.

## Details
- **Framework**: CrewAI
- **Tools used**: Git CLI Tool, Coral Server Tools
- **AI model**: OpenAI GPT-4.1
- **Date added**: 02/05/25

- **License**: MIT

## Use the Agent  

### 1. Clone & Install Dependencies


<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) is running on the Coral Server.  

```bash
# Clone the GitClone Agent repository
git clone https://github.com/Coral-Protocol/Coral-GitClone-Agent.git

# Navigate to the project directory
cd Coral-GitClone-Agent

# To run crewai agent, please switch to this branch:
git checkout coral-server-crewai
# If your multi-agents system includes crewai agent, ALL agents should be run on this server!

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```
This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

</details>

### 2. Configure Environment Variables
<details>

Get the API Key:
[OpenAI](https://platform.openai.com/api-keys)


```bash
cp -r .env.example .env
```

Add your API keys and any other required environment variables to the .env file.

</details>

### 3. Run Agent
<details>

Run the agent using `uv`:
```bash
uv run 1-crewai-GitCloneAgent.py
```
</details>

### 4. Example
<details>

```bash
# Input:
Please fetch the code of '2' PR in repo 'renxinxing123/camel-software-testing'.

# Output:
The PR was successfully checked out. Local repository path: /home/xinxing/coraliser-/coral_examples/github-repo-understanding+unit_test_advisor/camel-software-testing
```
</details>

## Creator Details
- **Name**: Xinxing
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)


</details>


## [Code diffs review agent](https://github.com/Coral-Protocol/Coral-CodeDiffReview-Agent)

Code diffs review agent compares changed files for a PR.

<details>

## Responsibility
The CodeDiffReview Agent automates code diff review for pull requests, making it easy to see what changed in a PR and summarize the impact.

## Details
- **Framework**: CAMEL-AI
- **Tools used**: GitHub MCP Server Tools, Coral Server Tools
- **AI model**: OpenAI GPT-4.1/Groq Llama 3.3 70B
- **Date added**: 02/05/25
- **License**: MIT

## Use the Agent  

### 1. Clone & Install Dependencies

<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) is running on the Coral Server.  

```bash
# Clone the CodeDiffReview Agent repository
git clone https://github.com/Coral-Protocol/Coral-CodeDiffReview-Agent.git

# Navigate to the project directory
cd Coral-CodeDiffReview-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```
This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

Copy the client sse.py from utils to mcp package (Linux/Mac):
```bash
cp -r utils/sse.py .venv/lib/python3.10/site-packages/mcp/client/sse.py
```

OR for Windows:
```bash
cp -r utils\sse.py .venv\Lib\site-packages\mcp\client\sse.py
```

</details>

### 2. Configure Environment Variables
<details>

Get the API Keys:
- [OpenAI API Key](https://platform.openai.com/api-keys)
- [Groq API Key](https://console.groq.com/keys)
- [GitHub Personal Access Token](https://github.com/settings/tokens)

Create a .env file in the project root:
```bash
cp -r .env.example .env
```

Add your API keys and any other required environment variables to the .env file.

Required environment variables:
- `OPENAI_API_KEY`
- `GROQ_API_KEY`
- `GITHUB_ACCESS_TOKEN`

</details>

### 3. Run Agent
<details>

Run the agent using `uv`:
```bash
uv run 2-camel-CodeDiffReviewAgent.py
```
</details>

### 4. Example
<details>

```bash
# Input:
Please get the code diffs for PR #2 in the repo `renxinxing123/camel-software-testing`

# Output:
Here are the code diffs/changed files for PR #2 in the repo `renxinxing123/camel-software-testing`:

---
**File:** `camel/toolkits/semantic_scholar_toolkit.py`

```diff
@@ -113,11 +113,11 @@ def fetch_paper_data_id(
             ]
 
         url = f"{self.base_url}/paper/{paper_id}"
-        query_params = {"fields": ",".join(fields)}
+        query_params = {"wrong_key": ",".join(fields)}
         try:
             response = requests.get(url, params=query_params)
             response.raise_for_status()
-            return response.json()
+            return {"wrong_key": "wrong_value"}
         except requests.exceptions.RequestException as e:
             return {
                 "error": f"Request failed: {e!s}",

**Summary:**
- The query parameter key was changed from `fields` to `wrong_key`.
- The return value was changed from the response JSON to a hardcoded dictionary: `{ "wrong_key": "wrong_value" }`.
```
</details>

## Creator Details
- **Name**: Xinxing
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)


</details>


## [Unit test runner agent](https://github.com/Coral-Protocol/Coral-UnitTestRunner-Agent)

Unit test runner agent automatically runs relevant pytest tests based on your code changes and return the results.

<details>

## Responsibility
The UnitTestRunner Agent automates running relevant unit tests for changed files in your repository, streamlining the testing process after code changes.

## Details
- **Framework**: LangChain
- **Tools used**: List Files Tool (Local), List File Tool (Local), CLI Tool, Coral Server Tools
- **AI model**: OpenAI GPT-4.1
- **Date added**: 02/05/25
- **License**: MIT

## Use the Agent  

### 1. Clone & Install Dependencies


<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) is running on the Coral Server.  

```bash
# Clone the UnitTestRunner Agent repository
git clone https://github.com/Coral-Protocol/Coral-UnitTestRunner-Agent.git

# Navigate to the project directory
cd Coral-UnitTestRunner-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```
This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

</details>

### 2. Configure Environment Variables
<details>

Get the API Key:
- [OpenAI API Key](https://platform.openai.com/api-keys)

Create a .env file in the project root:
```bash
cp -r .env.example .env
```

Add your API keys and any other required environment variables to the .env file.

Required environment variables:
- `OPENAI_API_KEY`




</details>

### 3. Run Agent
<details>

UnitTestRunner Agent is supposed to receive local repo path and changed files as inputs, so please also run [GitClone Agent](https://github.com/Coral-Protocol/Coral-GitClone-Agent) and [CodeDiffReview Agent](https://github.com/Coral-Protocol/Coral-CodeDiffReview-Agent) to get proper inputs.

Run the agent using `uv`:
```bash
uv run 3-langchain-UnitTestRunnerAgent.py
```
</details>

### 4. Example
<details>

```bash
# Input:
Could you please execute the unit test for changed file 'semantic_scholar_toolkit.py' in the local path 'camel-software-testing'

# Output:
Relevant test file: test/toolkits/test_semantic_scholar_functions.py

**Test Results:**
- Total tests: 11
- Passed: 9
- Failed: 2

**Failed tests:**
1. test_fetch_paper_data_id_success
2. test_fetch_paper_data_id_failure

**Summary:**
- The recent changes in `camel/toolkits/semantic_scholar_toolkit.py` caused failures in tests related to fetching paper data by ID. The function now returns `{'wrong_key': 'wrong_value'}` instead of the expected result or error dictionary.

**Pytest Output:**
============================= test session starts ==============================
platform linux -- Python 3.10.16, pytest-8.3.5, pluggy-1.5.0
rootdir: /home/xinxing/coraliser-/coral_examples/github-repo-understanding+unit_test_advisor/camel-software-testing
configfile: pyproject.toml
plugins: anyio-4.9.0, Faker-19.13.0, langsmith-0.3.42
collected 11 items

test/toolkits/test_semantic_scholar_functions.py ....FF.....             [100%]

=================================== FAILURES ===================================
_________ TestSemanticScholarToolkit.test_fetch_paper_data_id_failure __________
self = <test_semantic_scholar_functions.TestSemanticScholarToolkit testMethod=test_fetch_paper_data_id_failure>
mock_get = <MagicMock name='get' id='134648639737472'>
>       self.assertIn("error", response)
E       AssertionError: 'error' not found in {'wrong_key': 'wrong_value'}

test/toolkits/test_semantic_scholar_functions.py:110: AssertionError
_________ TestSemanticScholarToolkit.test_fetch_paper_data_id_success __________
self = <test_semantic_scholar_functions.TestSemanticScholarToolkit testMethod=test_fetch_paper_data_id_success>
mock_get = <MagicMock name='get' id='134648640270064'>
>       self.assertEqual(response, mock_response_data)
E       AssertionError: {'wrong_key': 'wrong_value'} != {'title': 'Paper Title by ID'}
E       - {'wrong_key': 'wrong_value'}
E       + {'title': 'Paper Title by ID'}

test/toolkits/test_semantic_scholar_functions.py:87: AssertionError
=========================== short test summary info ============================
FAILED test/toolkits/test_semantic_scholar_functions.py::TestSemanticScholarToolkit::test_fetch_paper_data_id_failure
FAILED test/toolkits/test_semantic_scholar_functions.py::TestSemanticScholarToolkit::test_fetch_paper_data_id_success
=================== 2 failed, 9 passed, 5 warnings in 1.49s ====================
```
</details>

## Creator Details
- **Name**: Xinxing
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)


</details>

## [Repo understanding agent](https://github.com/Coral-Protocol/Coral-RepoUnderstanding-Agent)

Repo understanding agent automatically analyzes key files in a specified GitHub repository and provides a concise summary of the project’s purpose, main modules, usage, and overall structure.

<details>

## Responsibility
The RepoUnderstanding Agent systematically inspects the most important files in a repository and delivers a clear, concise overview of the project structure and functionality.

## Details
- **Framework**: LangChain
- **Tools used**: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
- **AI model**: OpenAI GPT-4.1
- **Date added**: 02/05/25

- **License**: MIT

## Use the Agent  

### 1. Clone & Install Dependencies


<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) is running on the Coral Server.  

```bash
# Clone the RepoUnderstanding Agent repository
git clone https://github.com/Coral-Protocol/Coral-RepoUnderstanding-Agent.git

# Navigate to the project directory
cd Coral-RepoUnderstanding-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```
This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

</details>

### 2. Configure Environment Variables
<details>

Get the API Keys:
- [OpenAI API Key](https://platform.openai.com/api-keys)
- [GitHub Personal Access Token](https://github.com/settings/tokens)

Create a .env file in the project root:
```bash
cp -r .env.example .env
```

Add your API keys and any other required environment variables to the .env file.

Required environment variables:
- `OPENAI_API_KEY`
- `GITHUB_ACCESS_TOKEN`






</details>

### 3. Run Agent
<details>

Run the agent using `uv`:
```bash
uv run 4-langchain-RepoUnderstandingAgent.py
```
</details>

### 4. Example
<details>

```bash
# Input:
Please give me a comprehensive instruction of the master branch of Coral-Protocol/coral-server.

# Output:
Here is a comprehensive overview of the master branch of the Coral-Protocol/coral-server repository:

**Project Purpose & Main Functionality:**
- Coral Server implements the Coral Protocol, acting as a Model Context Protocol (MCP) server that enables communication between AI agents via a thread-based messaging system.
- It provides tools for agents to register, create/manage threads, send messages, mention other agents, and receive notifications when mentioned.
- The server is designed to facilitate multi-agent collaboration, with a focus on composability, scalability, and secure agent communication.

**Primary Components/Modules:**
- **src/main/kotlin/org/coralprotocol/coralserver/**: Core server logic, including the entry point (`Main.kt`), server setup (`CoralServer.kt`), session management, and orchestrator for agent lifecycle.
- **mcptools/**: Implements the MCP tools (e.g., list_agents, create_thread, add/remove participants, send_message, wait_for_mentions) that agents use to interact.
- **routes/**: Defines HTTP/SSE endpoints for agent and session communication.
- **orchestrator/**: Handles agent registration, spawning, and lifecycle management.
- **examples/camel-search-maths/**: Provides a practical example of multi-agent collaboration using the server with CAMEL agents.
- **application.yaml**: Configures applications and agent registry (including how agents are orchestrated and their environment variables).

**How to Use/Run the Project:**
- The server can be run via Gradle (`./gradlew run`) or as a standalone JAR after building.
- Supports multiple modes: standard I/O, SSE server (default, port 5555), and development mode.
- Agents connect to the server and use the available MCP tools for communication.
- Example workflow: Start the server, then run the example agents (math, search, interface) in the example directory. The agents collaborate to answer user queries.

**Noteworthy Implementation Details:**
- Built in Kotlin, using Ktor for the server and SSE/WebSocket support.
- Extensible agent registry and orchestrator allow for local and (planned) remote agent management.
- YAML-based configuration for applications and agent orchestration.
- Designed for open, composable AI agent societies, with a focus on secure, scalable, and flexible communication.
- Early-stage project with ongoing development toward remote mode and expanded features.

**Summary:**
Coral Server is a foundation for multi-agent AI systems, enabling agents to communicate, collaborate, and manage conversations through a standardized protocol and set of tools. It is highly extensible and intended as open infrastructure for the "Society of AI Agents." The project is not yet production-ready but provides a robust starting point for building complex agent-based systems.
```
</details>

## Creator Details
- **Name**: Xinxing
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>


## [Repo unit test advisor agent](https://github.com/Coral-Protocol/Coral-RepoUnitTestAdvisor-Agent)

Repo unit test advisor agent evaluates if unit tests in a specified repo and branch sufficiently cover target files, and suggests if more tests are needed.

<details>

## Responsibility
The RepoUnitTestAdvisor Agent analyzes test coverage for target files in a repository and branch, and recommends additional tests if needed.

## Details
- **Framework**: LangChain
- **Tools used**: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
- **AI model**: OpenAI GPT-4.1
- **Date added**: 02/05/25
- **License**: MIT

## Use the Agent  

### 1. Clone & Install Dependencies


<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) is running on the Coral Server.  

```bash
# Clone the RepoUnitTestAdvisor Agent repository
git clone https://github.com/Coral-Protocol/Coral-RepoUnitTestAdvisor-Agent.git

# Navigate to the project directory
cd Coral-RepoUnitTestAdvisor-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```
This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

</details>

### 2. Configure Environment Variables
<details>

Get the API Keys:
- [OpenAI API Key](https://platform.openai.com/api-keys)
- [GitHub Personal Access Token](https://github.com/settings/tokens)

Create a .env file in the project root:
```bash
cp -r .env.example .env
```

Add your API keys and any other required environment variables to the .env file.

Required environment variables:
- `OPENAI_API_KEY`
- `GITHUB_ACCESS_TOKEN`

</details>

### 3. Run Agent
<details>

Run the agent using `uv`:
```bash
uv run 5-langchain-RepoUnitTestAdvisorAgent.py
```
</details>

### 4. Example
<details>

```bash
# Input:
Could you please help me check if the unit test file for new_semantic_scholar_toolkit.py in the branch `new-semantic-scholar-toolkit` of the repo `renxinxing123/camel-software-testing` fully cover all necessary cases? Are there any additional tests that should be added?

# Output:
**Coverage Summary for `camel/toolkits/new_semantic_scholar_toolkit.py`:**

**Target File Overview:**
This file defines the `SemanticScholarToolkit` class, which provides methods to interact with the Semantic Scholar API, including:
- `fetch_paper_data_title`
- `fetch_paper_data_id`
- `fetch_bulk_paper_data`
- `fetch_recommended_papers`
- `fetch_author_data`
- `get_tools`

**Associated Unit Test File:**
- `test/toolkits/new_test_semantic_scholar_functions.py`

**Test Coverage Analysis:**
- **fetch_paper_data_title**: Tested for both successful (200) and error (non-200) responses, including correct parameter passing and error handling.
- **fetch_paper_data_id**: Tested for successful and error responses, including correct URL and parameter usage, and error message propagation.
- **fetch_bulk_paper_data**: Tested for both successful and error responses, including parameter checks and error handling.
- **fetch_recommended_papers**: Tested for successful and error (non-200) responses, including correct request body, URL, and error handling.
- **fetch_author_data**: Tested for both successful and error responses, including correct request body, parameter passing, and error handling.
- **get_tools**: Explicitly tested to ensure all toolkit functions are included and correctly referenced.

**Aspects Covered:**
- Typical use cases (successful API responses)
- Error handling for non-200 responses and exceptions
- Parameter and URL correctness
- Mocking of external dependencies (`requests.get` and `requests.post`)
- Toolkit registration and function referencing

**Potential Gaps:**
- Edge cases for malformed or unexpected API responses (e.g., invalid JSON, network timeouts) are partially covered via exception handling, but not all possible error scenarios (like timeouts or malformed data) are explicitly tested.
- File saving logic (`save_to_file=True` in `fetch_recommended_papers` and `fetch_author_data`) is not tested; tests always use `save_to_file=False`.
- No tests for very large input lists or stress testing (e.g., very large `positive_paper_ids` or `ids`).
- No tests for optional `fields` parameter variations (e.g., passing custom field lists).

**Recommendations:**
- Add tests for the `save_to_file=True` scenario to ensure file writing works and handles file I/O errors gracefully.
- Add tests for malformed JSON responses (simulate API returning invalid JSON).
- Add tests for network timeouts and other `requests` exceptions (e.g., `Timeout`, `ConnectionError`).
- Add tests for custom `fields` parameter values to ensure correct query construction.
- Consider adding stress tests for large input lists if performance or memory is a concern.

**Conclusion:**
The current unit tests provide strong coverage of the main functionality and error handling for the toolkit. Addressing the above recommendations would further strengthen robustness, especially for edge cases and file I/O.
```
</details>

## Creator Details
- **Name**: Xinxing
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)


</details>


## [Repo doc consistency checker agent](https://github.com/Coral-Protocol/Coral-RepoDocConsistencyChecker-Agent)

Repo doc consistency checker agent checks if documentation in a specified repo and branch is up-to-date.

<details>

## Responsibility
The RepoDocConsistencyChecker Agent checks if documentation is consistent with recent code changes in a repository and branch, and recommends updates if needed.

## Details
- **Framework**: LangChain
- **Tools used**: PyGithub List File Tool, PyGithub Read File Tool, Coral Server Tools
- **AI model**: OpenAI GPT-4.1
- **Date added**: 02/05/25


## Use the Agent  

### 1. Clone & Install Dependencies


<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) is running on the Coral Server.  

```bash
# Clone the RepoDocConsistencyChecker Agent repository
git clone https://github.com/Coral-Protocol/Coral-RepoDocConsistencyChecker-Agent.git

# Navigate to the project directory
cd Coral-RepoDocConsistencyChecker-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```
This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

</details>

### 2. Configure Environment Variables
<details>

Get the API Keys:
- [OpenAI API Key](https://platform.openai.com/api-keys)
- [GitHub Personal Access Token](https://github.com/settings/tokens)

Create a .env file in the project root:
```bash
cp -r .env.example .env
```

Add your API keys and any other required environment variables to the .env file.

Required environment variables:
- `OPENAI_API_KEY`
- `GITHUB_ACCESS_TOKEN`

</details>

### 3. Run Agent
<details>

Run the agent using `uv`:
```bash
uv run 6-langchain-RepoDocConsistencyCheckerAgent.py
```
</details>

### 4. Example
<details>

```bash
# Input:
Could you please help me check if the doc in the branch 'repo-understanding+unit-test-advice' of the repo 'renxinxing123/software-testing-agents-test' covered all changes from the updated file '4-langchain-RepoUnderstandingAgent.py' and '5-langchain-RepoUnitTestAdvisorAgent.py'.

# Output:
**Documentation Consistency Analysis for Updated Files:**

**Changed Files:**
- 4-langchain-RepoUnderstandingAgent.py
- 5-langchain-RepoUnitTestAdvisorAgent.py

**Relevant Documentation File Reviewed:**
- README.md

---

**Analysis:**

Both changed files implement new or updated agents for repository understanding and unit test advising. The README.md provides an overview of the agents, their responsibilities, and usage instructions for the system. It describes the roles of the "RepoUnderstandingAgent" and "RepoUnitTestAdvisorAgent" in the context of the multi-agent workflow, including their purpose and how they interact with the system.

**Findings:**
- The README.md does mention the existence and purpose of these agents, but it does not provide detailed usage instructions, configuration options, or specific workflow examples for these two agents.
- There is no section in the README.md that explains how to invoke these agents directly, what input parameters they require, or what output to expect.
- The agent scripts themselves contain detailed docstrings and workflow comments, but this information is not surfaced in the documentation.

**Recommendations:**
1. **Add Agent-Specific Sections:**
   - Add dedicated subsections in the README.md for "RepoUnderstandingAgent" and "RepoUnitTestAdvisorAgent".
   - Include a brief description, usage instructions (how to invoke, required arguments), and example input/output for each agent.
2. **Document Parameters and Workflow:**
   - Clearly document any environment variables, configuration, or prerequisites specific to these agents.
   - Provide a sample workflow showing how these agents fit into the overall system (e.g., how to trigger a repository analysis or test coverage evaluation).
3. **Update Usage Examples:**
   - If these agents can be invoked independently, add example commands or API calls.
   - If they are only used as part of the multi-agent workflow, clarify their role and how users interact with them.

**Summary:**
- The documentation is **partially up-to-date**: the agents are mentioned, but detailed usage and configuration instructions for the updated files are missing.
- Updating the README.md as recommended will improve clarity and help users leverage the new/updated agent functionalities.

Let me know if you need example documentation text or further breakdowns!
```
</details>

## Creator Details
- **Name**: Xinxing
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)


</details>

---

# Enterprise

## [PandasAI Agent](https://github.com/Coral-Protocol/Pandas-ai-Agent)

PandasAI Agent lets you ask natural language questions about your Excel or CSV files using a local LLM (e.g., Llama 3.1/Qwen3), just provide the file path and your query to get instant answers.

<details>

## Responsibility
The PandasAI Agent enables natural language querying of tabular data (Excel/CSV) using a local LLM through PandasAI, making data analysis accessible and conversational.

## Details
- **Framework**: LangChain
- **Tools used**: PandasAI Tools, Coral MCP Tools
- **AI model**: Llama3.1/Qwen3 via Ollama
- **Date added**: 04/06/25
- **Reference**: [PandasAI Agent](https://pandas-ai.com/)
- **License**: MIT

## Use the Agent

### 1. Install and Run Ollama (for Local LLM)
<details>

PandasAI Agent uses Ollama to run local LLMs. Please make sure you have Ollama installed and the desired model downloaded before running the agent.

**Step 1: Install Ollama**

- **Linux/macOS:**
  Follow the official instructions: [https://ollama.com/download](https://ollama.com/download)
  Or run:
  ```bash
  curl -fsSL https://ollama.com/install.sh | sh
  ```
- **Windows:**
  Download the installer from [Ollama's website](https://ollama.com/download).

**Step 2: Download Local model**

```bash
ollama pull llama3.1:latest
ollama pull qwen3:latest
```

**Step 3: Start Ollama Service**

Ollama usually starts automatically. If not, start it manually:
```bash
ollama serve
```

**Step 4: Verify the model is running**

```bash
ollama list
```
Make sure no errors occur and Ollama is running at `http://localhost:11434`.

</details>

### 2. Clone & Install Dependencies

<details>  

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) is running on the Coral Server.  

```bash
# Clone the PandasAI Agent repository
git clone https://github.com/Coral-Protocol/Pandas-ai-Agent.git

# Navigate to the project directory
cd Pandas-ai-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```
This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

</details>

### 3. Configure Environment Variables
<details>

Get the API Key:
[OpenAI](https://platform.openai.com/api-keys)

Create a .env file in the project root:
```bash
cp -r env_sample .env
```

Add your API keys and any other required environment variables to the .env file.

</details>

### 4. Run Agent
<details>

Run the agent using `uv`:
```bash
uv run 1-langchain-PandasAiAgent.py
```
</details>

### 5. Example
<details>

```bash
# Input:
Question: What are the total number of columns in the coral_public_repo_docs.xlsx

# Output:
Answer: The total number of columns in the coral_public_repo_docs.xlsx is 4.
```

**🎬 [Watch Video Demo](https://youtu.be/aq6du6XRzGE)**

</details>

## Creator Details
- **Name**: Xinxing
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)


</details>

---

# Voice AI Agents

## [Voice Interface Agent](https://github.com/Coral-Protocol/Voice-Interface-Agent)

Real-time voice interface coordinating communication between users and specialized agents via LiveKit and Coral Protocol.

<details>

## Responsibility
The LiveKit Voice Interface Agent acts as a central coordinator, connecting users with task-specific agents via real-time voice communication. It captures user voice input, routes queries to the appropriate agent, and responds using a clean, real-time voice channel, leveraging LiveKit and Coral Protocol for seamless integration.

## Details
- **Framework**: LiveKit Agents
- **Tools used**: LiveKit, OpenAI LLM
- **AI model**: GPT-4
- **Date added**: June 2025
- **License**: MIT


## Use the Agent  

### 1. Clone & Install Dependencies
Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system
<details>


Ensure you have Python and [uv](https://github.com/astral-sh/uv) installed.

```bash
# In a new terminal clone the repository:
git clone https://github.com/Coral-Protocol/Voice-Interface-Agent.git

# Navigate to the project directory:
cd Voice-Interface-Agent
# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```

</details>

### 2. Configure Environment Variables

<details>

Copy the example file and update it with your credentials:

```bash
cp -r .env.example .env
```

Required environment variables:

* `LIVEKIT_URL`
* `LIVEKIT_API_KEY` ([Get LiveKit API Key](https://cloud.livekit.io/))
* `LIVEKIT_API_SECRET` ([Get LiveKit API Secret](https://cloud.livekit.io/))
* `OPENAI_API_KEY` ([Get OpenAI API Key](https://platform.openai.com/api-keys))

</details>

### 3. Run Agent

<details>

Run the agent in terminal (console) mode:

```bash
uv run python main.py console
```

</details>

### 4. Example

<details>

```bash
# Speak your query naturally after launching the agent.

# The system will:
# - Capture your voice input
# - Route the query to the appropriate agent
# - Respond using a clean, real-time voice channel
```

</details>

## Creator Details
- **Name**: Ahsen Tahir
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>

## [Medical Office Triage Voice Agent](https://github.com/Coral-Protocol/Medical-Office-Triage-Voice-Agent)

Automates patient triage and department routing through real-time voice interactions in medical offices.

<details>

## Responsibility
A real-time voice agent for medical offices that automates patient intake, support, and billing routing. **Note:** The prompts in this agent are not for a multi-agent system; it currently works as a standalone agent, does not require interface agents, but will use Coral tools. It is not continuously using the `wait_for_mention` tool to receive commands from other agents.

## Details
- **Framework:** LiveKit Agents
- **Tools Used:** Deepgram STT, Cartesia TTS, OpenAI LLM, Silero VAD, LiveKit Plugins
- **AI Model:** GPT-4o-mini
- **Date Added:** June 2025
- **License:** MIT
- **Original Source:** [LiveKit Python Agents Examples - Medical Office Triage](https://github.com/livekit-examples/python-agents-examples/tree/main/complex-agents/medical_office_triage)

## Use the Agent

### 1. Clone & Install Dependencies

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system. This agent does not require the Interface Agent and is not designed for multi-agent workflows.
<details>

```bash
# In a new terminal clone the repository:
git clone https://github.com/Coral-Protocol/Medical-Office-Triage-Voice-Agent.git

# Navigate to the project directory:
cd Medical-Office-Triage-Voice-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```

</details>

### 2. Configure Environment Variables
<details>

Copy the example file and add your API keys:

```bash
cp .env.example .env
```

Update `.env` with:
- `LIVEKIT_URL` ([Get LiveKit Url](https://cloud.livekit.io/))
- `LIVEKIT_API_KEY` ([Get LiveKit API Key](https://cloud.livekit.io/))
- `LIVEKIT_API_SECRET` ([Get LiveKit API Secret](https://cloud.livekit.io/))
- `OPENAI_API_KEY` ([Get OpenAI API Key](https://platform.openai.com/api-keys))
- `DEEPGRAM_API_KEY` ([Get Deepgram API Key](https://deepgram.com/))
- `CARTESIA_API_KEY` ([Get Cartesia API Key](https://cartesia.ai/))

</details>

### 3. Run Agent
<details>

```bash
uv run triage.py console
```

</details>

## Agent System

- **Triage Agent:** Initial patient intake, determines appropriate department routing
- **Support Agent:** Handles medical services, appointments, and general patient support inquiries
- **Billing Agent:** Manages insurance inquiries, payment questions, and billing support

## Technical Features

- **Multi-Agent Voice System:** Three specialized AI agents working seamlessly together
- **Real-time Voice Processing:** Deepgram speech-to-text, Cartesia text-to-speech, OpenAI language understanding
- **Intelligent Routing:** Automatic patient transfer between departments based on conversation analysis

## Usage Examples
<details>

1. **Start the application using the console command** - The system initializes with all three agents ready
2. **Begin speaking when you hear the system is ready** - You'll be connected to the Triage Agent first
3. **Triage Agent interaction** - The Triage Agent will:
   - Listen to your initial request or concern
   - Ask clarifying questions about your medical office needs
   - Determine whether you need appointment scheduling, medical support, or billing assistance
   - Route you to the appropriate specialist agent based on your needs
4. **Automatic transfer to specialist agents**:
   - **Support Agent** - If you need:
     - Medical appointment scheduling
     - General patient support inquiries
     - Information about medical services
     - Health-related questions and guidance
   - **Billing Agent** - If you need:
     - Insurance verification and claims
     - Payment processing and billing questions
     - Cost estimates for procedures
     - Financial assistance programs
5. **Continue the conversation naturally** - Once transferred:
   - The specialist agent has full context of your previous conversation
   - You can ask follow-up questions specific to that department
   - The agent can transfer you back to Triage or to another specialist if needed
   - All conversation history is preserved throughout transfers

</details>

## Creator Details
- **Name:** Ahsen Tahir
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)
</details>

## [Restaurant Voice Agent System](https://github.com/Coral-Protocol/Restuarant-Voice-Agent)

Manages restaurant reservations, orders, and checkout using a multi-agent voice conversation system.

<details>

## Responsibility
A multi-agent voice system for restaurants, enabling natural, seamless voice-based reservations, orders, and payments by routing conversations between specialized agents.

## Details
- **Framework:** LiveKit Agents
- **Tools Used:** Deepgram STT, Cartesia TTS, OpenAI LLM, Silero VAD
- **AI Model:** GPT-4
- **Date Added:** January 2025
- **License:** MIT
- **Original Source:** [Restaurant Voice Agent System](https://github.com/livekit/agents/blob/main/examples/voice_agents/restaurant_agent.py)

## Use the Agent

### 1. Clone & Install Dependencies

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system. If you are trying to run Restaurant Voice Agent and require an input, you can either create your agent which communicates on the coral server or run and register the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) on the Coral Server.

<details>

```bash
# In a new terminal clone the repository:
git clone https://github.com/Coral-Protocol/Restuarant-Voice-Agent.git

# Navigate to the project directory:
cd Restuarant-Voice-Agent
# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```

</details>

### 2. Configure Environment Variables

<details>

Copy the example file and add your API keys:

```bash
cp .env.example .env
```

Update `.env` with:
- `LIVEKIT_URL`
- `LIVEKIT_API_KEY` ([Get LiveKit API Key](https://cloud.livekit.io/))
- `LIVEKIT_API_SECRET` ([Get LiveKit API Secret](https://cloud.livekit.io/))
- `OPENAI_API_KEY` ([Get OpenAI API Key](https://platform.openai.com/api-keys))
- `DEEPGRAM_API_KEY` ([Get Deepgram API Key](https://deepgram.com/))
- `CARTESIA_API_KEY` ([Get Cartesia API Key](https://play.cartesia.ai/keys))

</details>

## 3. Run Agent
<details>

```bash
uv run python main.py console
```

</details>

## 4. Example
<details>

## Agent System

### 🏪 Greeter Agent
Welcomes customers, presents menu (Pizza $10, Salad $5, Ice Cream $3, Coffee $2), and routes to specialized agents.

### 📅 Reservation Agent
Handles dining reservations - collects time, customer name, and phone number.

### 🥡 Takeaway Agent
Processes food orders - takes orders from menu, clarifies requests, confirms details.

### 💳 Checkout Agent
Handles payments - calculates expenses, collects contact info and credit card details.

## Usage Examples

<details>

**Getting Started:**
1. Start the agent using `uv run python main.py console`
2. The Greeter Agent will automatically welcome you to the restaurant
3. Say "Hi!" or any greeting to initiate the conversation
4. The agent will then listen to other agent calling it (for example interface agent)
5. Continue your conversation naturally - the system will route you to the appropriate specialized agent

**Making a Reservation:**
1. Say: "I'd like to make a reservation"
2. The system routes you to the Reservation Agent
3. Provide preferred time, name, and phone
4. Confirm details

**Ordering Takeaway:**
1. Say: "I want to order food"
2. The system routes you to the Takeaway Agent
3. Place order from menu
4. Get routed to Checkout Agent for payment
5. Provide payment information and complete transaction

</details>

## Creator Details
- **Name:** Ahsen Tahir
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>
</details>

## [Voice French Agent](https://github.com/Coral-Protocol/Voice-French-Agent)

Multilingual voice assistant translating English speech to fluent French responses in real time.

<details>

## Responsibility
A real-time multilingual voice assistant that listens to English speech, translates it to French, and responds in natural French voice using advanced AI and speech technologies.

## Details
- **Framework:** LiveKit Agents
- **Tools Used:** Deepgram STT, ElevenLabs TTS, OpenAI LLM, LiveKit Plugins
- **AI Model:** GPT-4
- **Date Added:** June 2025
- **License:** MIT
- **Original Source:** [Voice French Agent](https://github.com/livekit-examples/python-agents-examples/blob/main/translators/pipeline_translator.py)

## Use the Agent

### 1. Clone & Install Dependencies

Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system. If you are trying to run Voice French Agent and require an input, you can either create your agent which communicates on the coral server or run and register the [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) on the Coral Server.
<details>

```bash
# In a new terminal clone the repository:
git clone https://github.com/Coral-Protocol/Voice-French-Agent.git

# Navigate to the project directory:
cd Voice-French-Agent

# Install `uv`:
pip install uv

# Install dependencies from `pyproject.toml` using `uv`:
uv sync
```

</details>

### 2. Configure Environment Variables
<details>

Copy the example file and add your API keys:

```bash
cp .env.example .env
```

Update `.env` with:
- `LIVEKIT_URL`  ([Get LiveKit Url](https://cloud.livekit.io/))
- `LIVEKIT_API_KEY` ([Get LiveKit API Key](https://cloud.livekit.io/))
- `LIVEKIT_API_SECRET` ([Get LiveKit API Secret](https://cloud.livekit.io/))
- `OPENAI_API_KEY` ([Get OpenAI API Key](https://platform.openai.com/api-keys))
- `DEEPGRAM_API_KEY` ([Get Deepgram API Key](https://deepgram.com/))
- `ELEVENLABS_API_KEY` ([Get ElevenLabs API Key](https://elevenlabs.io/app/settings/api-keys))

</details>

### 3. Run Agent
<details>

Start the agent with voice input/output:

```bash
uv run python main.py console
```

</details>

## Agent System

- **English Speech Recognition:** via Deepgram
- **AI Translation to French:** powered by OpenAI
- **French Voice Output:** using ElevenLabs
- **Noise Cancellation:** with LiveKit plugins

## Usage Examples
<details>

1. Start the agent.
2. Speak in English.
3. The agent:
   - Transcribes your speech.
   - Translates to French.
   - Responds in natural French voice.

**For a Multi-Agent-System:**
```python
# Other agents can communicate with French agent like this:
# 1. Send message to french_agent via MCP
# 2. French agent will notify interface agent
# 3. Users can then speak directly with French agent
# 4. All responses are in French via speech
```

</details>

## Creator Details
- **Name:** Ahsen Tahir
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)



</details>

---

# Know More 🐙  
Learn more about the Coral Protocol at [Coral Documentation](https://docs.coralprotocol.org/CoralDoc/Introduction/WhatisCoralProtocol).
