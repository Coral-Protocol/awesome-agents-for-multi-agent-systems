# Awesome agents for your multi-agent systems


Dive into the vibrant Coral Reef, a thriving ecosystem of AI agents crafted by the Coral Protocol! Our reef splits into various categories, for various use case:

1. General
2. Research/ Scrapping
3. Software
4. Enterprise
5. Voice Agents

<img width="1300" alt="Coral-AI_Agents_Landscape_v3b" src="https://github.com/user-attachments/assets/2bf43f96-a4e6-41bd-913e-6c8ca44e87af" />

---

# General

## [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent)

User Interaction Agent is the main interface for receiving user instructions, coordinating multi-agent tasks, and logging conversations via the terminal.

<details>

## Responsibility

**User Interaction Agent** acts as the main interface for coordinating user instructions and managing multi-agent tasks. It interacts with the user via terminal and orchestrates requests among various agents, ensuring seamless workflow and conversation logging.


## Details
- **Framework**: LangChain
- **Tools used**: Coral MCP Tools, ask_human Tool (human-in-the-loop)
- **AI model**: GPT-4o
- **Date added**: June 4, 2025
- **License**: MIT 

## Clone & Install Dependencies

1. Run [Coral Server](https://github.com/Coral-Protocol/coral-server)
<details>

This agent runs on Coral Server, follow the instrcutions below to run the server. In a new terminal clone the repository:


```bash
git clone https://github.com/Coral-Protocol/coral-server.git
```

Navigate to the project directory:
```bash
cd coral-server
```
Run the server
```bash
cd ./gradlew run
```
</details>

2. Agent Installation

In a new terminal clone the repository
```bash
git clone https://github.com/Coral-Protocol/Coral-Interface-Agent.git
```
Navigate to the project directory:
```bash
cd Coral-Interface-Agent
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
Get the API Key:
[OpenAI](https://platform.openai.com/api-keys)


Create .env file in project root
```bash
echo -e "OPENAI_API_KEY=your_openai_api_key" > .env
```

OR Directly export in terminal

```bash
export OPENAI_API_KEY=
```

## Run Agent
Run the agent using `uv`:
```bash
uv run python 0-langchain-interface.py
```

## Example Output

```text
Agent: How can I assist you today?
```

## Creator Details
- **Name**: Suman Deb
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>

---

# Research/ Scrapping

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

## Clone & Install Dependencies

1. Run [Coral Server](https://github.com/Coral-Protocol/coral-server)
<details>

This agent runs on Coral Server, follow the instrcutions below to run the server. In a new terminal clone the repository:


```bash
git clone https://github.com/Coral-Protocol/coral-server.git
```

Navigate to the project directory:
```bash
cd coral-server
```
Run the server
```bash
cd ./gradlew run
```
</details>

2. Run [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent)
<details>


If you are trying to run Open Deep Research agent and require an input, you can either create your agent which communicates on the coral server or run and register the Interface Agent on the Coral Server. In a new terminal clone the repository:


```bash
git clone https://github.com/Coral-Protocol/Coral-Interface-Agent.git
```
Navigate to the project directory:
```bash
cd Coral-Interface-Agent
```

Install `uv`:
```bash
pip install uv
```
Install dependencies from `pyproject.toml` using `uv`:
```bash
uv sync
```

Configure API Key
```bash
export OPENAI_API_KEY=
```

Run the agent using `uv`:
```bash
uv run python 0-langchain-interface.py
```

</details>


3. Agent Installation

<details>

In a new terminal clone the repository:
```bash
git clone https://github.com/Coral-Protocol/Coral-OpenDeepResearch-Agent.git
```

Navigate to the project directory:
```bash
cd Coral-OpenDeepResearch-Agent
```

Install `uv`:
```bash
pip install uv
```

Install dependencies from `pyproject.toml` using `uv`:
```bash
uv sync
```

This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

</details>

## Configure Environment Variables
Get the API Key:
[Linkup](https://app.linkup.so/api-keys)
[OpenAI](https://platform.openai.com/api-keys)


Create .env file in project root
```bash
echo -e "OPENAI_API_KEY=your_openai_api_key\nLINKUP_API_KEY=your_linkup_api_key" > .env
```

OR Directly export in terminal

```bash
export OPENAI_API_KEY=
```

```bash
export LINKUP_API_KEY=
```

## Run Agent
Run the agent using `uv`:
```bash
uv run python langchain_open_deep_research.py
```

## Example Output
```
(Sample too big to post, check temp folder)
```

## Creator Details
- **Name**: Suman Deb
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>

## [Firecrawl Coral Agent](https://github.com/Coral-Protocol/firecrawl-coral-agent.git)
The Firecrawl Coral Agent is an open-source agent designed for comprehensive web scraping, crawling, and data extraction tasks.

<details>

### Responsibility
The Firecrawl Coral Agent is an open-source agent designed for comprehensive web scraping, crawling, and data extraction tasks. It excels in structured data extraction and deep research by leveraging a multi-agent architecture to efficiently navigate, search, and analyze web content.


### Details
- **Framework**: LangChain
- **Tools used**: Firecrawl MCP Server Tools, Coral Server Tools
- **AI model**: OpenAI GPT-4o
- **Date added**: June 4, 2025
- **Reference**: [Firecrawl MCP Repo](https://github.com/mendableai/firecrawl)
- **License**: MIT

### Clone & Install Dependencies
Clone the repository:
```bash
git clone https://github.com/Coral-Protocol/firecrawl-coral-agent.git
```

Navigate to the project directory:
```bash
cd firecrawl-coral-agent
```

Install `uv`:
```bash
pip install uv
```

Install dependencies from `pyproject.toml` using `uv`:
```bash
uv sync
```

This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

### Configure Environment Variables
Get the API Key:
[OpenAI](https://platform.openai.com/api-keys)
[Firecrawl](https://www.firecrawl.dev/app/api-keys)

Rename the sample environment file to `.env` and add the keys:
```bash
mv .env_sample .env
```
Check if the environment file has correct URL for Coral Server and adjust the parameters accordingly.

### Run Agent
Run the agent using `uv`:
```bash
uv run python firecrawl_coral_agent.py
```

### Example Output
```
The Model Context Protocol (MCP) is an innovative open-source standard designed to enhance the interaction between artificial intelligence (AI) models and external tools and data sources. Introduced by Anthropic in November 2024, MCP addresses a critical challenge in the AI space by enabling seamless integration among diverse applications, particularly large language models (LLMs). This protocol streamlines data sharing and context management, offering a cohesive framework that allows AI systems to access real-time information efficiently. By eliminating the need for custom integrations, MCP fosters a more dynamic and interconnected AI ecosystem, thus empowering developers to create responsive and context-aware applications.

```

### Creator Details
- **Name**: Suman Deb
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>

---

# Software

## [Github Coral Agent](https://github.com/Coral-Protocol/github-coral-agent.git)

The Github Coral Agent is an open-source agent designed for managing GitHub repositories. It supports creating, updating, and searching for repositories and files, handling issues and pull requests, and facilitating collaboration through comments and reviews using a multi-agent architecture.

<details>

## Details
- **Framework**: LangChain
- **Tools used**: GitHub MCP Server Tools, Coral Server Tools
- **AI model**: OpenAI GPT-4
- **Date added**: June 4, 2025
- **Reference**: [GitHub MCP Repo](https://github.com/github/github-mcp-server)
- **License**: MIT

## Clone & Install Dependencies
Clone the repository:
```bash
git clone https://github.com/Coral-Protocol/github-coral-agent.git
```

Navigate to the project directory:
```bash
cd github-coral-agent
```

Install `uv`:
```bash
pip install uv
```

Install dependencies from `pyproject.toml` using `uv`:
```bash
uv sync
```

This command will read the `pyproject.toml` file and install all specified dependencies in a virtual environment managed by `uv`.

## Configure Environment Variables
Get the API Key:
[OpenAI](https://platform.openai.com/api-keys)

Create .env file in project root:
```bash
echo -e "OPENAI_API_KEY=your_openai_api_key" > .env
```

OR Directly export in terminal:
```bash
export OPENAI_API_KEY=
```

## Run Agent
Run the agent using `uv`:
```bash
uv run python github_coral_agent.py
```

## Example Output
```
(Sample too big to post, check temp folder)
```

## Creator Details
- **Name**: Suman
- **Affiliation**: Coral Protocol
- **Contact**: [Discord](https://discord.com/invite/Xjm892dtt3)

</details>


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

**How to obtain API keys:**

* **OPENAI_API_KEY:**
  Sign up at [platform.openai.com](https://platform.openai.com/), go to “API Keys” under your account, and click “Create new secret key.”


### Run agent command

```bash
python 1-crewai-GitCloneAgent.py
```

### Example output

```bash
The PR was successfully checked out. Local repository path: /home/xinxing/coraliser-/coral_examples/github-repo-understanding+unit_test_advisor/camel-software-testing
```

### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: xinxing@coralprotocol.org

</details>


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

**How to obtain API keys:**

* **OPENAI_API_KEY:**
  Sign up at [platform.openai.com](https://platform.openai.com/), go to “API Keys” under your account, and click “Create new secret key.”

* **GROQ_API_KEY:**
  Register at [groq.com](https://groq.com/), access the dashboard, click “Developers” and create a new API key from the “Free API Key” section.

* **GITHUB_ACCESS_TOKEN:**
  Log in to [github.com](https://github.com/), go to **Settings → Developer settings → Personal access tokens**, then “Generate new token,” select the required scopes, and copy the generated token.


### Run agent command

```bash
python 2-camel-CodeDiffReviewAgent.py
```

### Example output

```bash
Here are the code diffs/changed files for PR #2 in the repo `renxinxing123/camel-software-testing`:

---
**File:** `camel/toolkits/semantic_scholar_toolkit.py`

```diff
@@ -113,11 +113,11 @@ def fetch_paper_data_id(
             ]
 
         url = f&quot;{self.base_url}/paper/{paper_id}&quot;
-        query_params = {&quot;fields&quot;: &quot;,&quot;.join(fields)}
+        query_params = {&quot;wrong_key&quot;: &quot;,&quot;.join(fields)}
         try:
             response = requests.get(url, params=query_params)
             response.raise_for_status()
-            return response.json()
+            return {&quot;wrong_key&quot;: &quot;wrong_value&quot;}
         except requests.exceptions.RequestException as e:
             return {
                 &quot;error&quot;: f&quot;Request failed: {e!s}&quot;,

**Summary:**
- The query parameter key was changed from `fields` to `wrong_key`.
- The return value was changed from the response JSON to a hardcoded dictionary: `{ &quot;wrong_key&quot;: &quot;wrong_value&quot; }`.
```

### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: xinxing@coralprotocol.org

</details>


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

**How to obtain API keys:**

* **OPENAI_API_KEY:**
  Sign up at [platform.openai.com](https://platform.openai.com/), go to “API Keys” under your account, and click “Create new secret key.”

### Run agent command

```bash
python 3-langchain-UnitTestRunnerAgent.py
```

### Example output

```bash
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
self = &lt;test_semantic_scholar_functions.TestSemanticScholarToolkit testMethod=test_fetch_paper_data_id_failure&gt;
mock_get = &lt;MagicMock name='get' id='134648639737472'&gt;
&gt;       self.assertIn(&quot;error&quot;, response)
E       AssertionError: 'error' not found in {'wrong_key': 'wrong_value'}

test/toolkits/test_semantic_scholar_functions.py:110: AssertionError
_________ TestSemanticScholarToolkit.test_fetch_paper_data_id_success __________
self = &lt;test_semantic_scholar_functions.TestSemanticScholarToolkit testMethod=test_fetch_paper_data_id_success&gt;
mock_get = &lt;MagicMock name='get' id='134648640270064'&gt;
&gt;       self.assertEqual(response, mock_response_data)
E       AssertionError: {'wrong_key': 'wrong_value'} != {'title': 'Paper Title by ID'}
E       - {'wrong_key': 'wrong_value'}
E       + {'title': 'Paper Title by ID'}

test/toolkits/test_semantic_scholar_functions.py:87: AssertionError
=========================== short test summary info ============================
FAILED test/toolkits/test_semantic_scholar_functions.py::TestSemanticScholarToolkit::test_fetch_paper_data_id_failure
FAILED test/toolkits/test_semantic_scholar_functions.py::TestSemanticScholarToolkit::test_fetch_paper_data_id_success
=================== 2 failed, 9 passed, 5 warnings in 1.49s ====================
```

### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: xinxing@coralprotocol.org

</details>

## [Repo understanding agent](https://github.com/Coral-Protocol/Coral-RepoUnderstanding-Agent)

Repo understanding agent automatically analyzes key files in a specified GitHub repository and provides a concise summary of the project’s purpose, main modules, usage, and overall structure.

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

**How to obtain API keys:**

* **OPENAI_API_KEY:**
  Sign up at [platform.openai.com](https://platform.openai.com/), go to “API Keys” under your account, and click “Create new secret key.”

* **GITHUB_ACCESS_TOKEN:**
  Log in to [github.com](https://github.com/), go to **Settings → Developer settings → Personal access tokens**, then “Generate new token,” select the required scopes, and copy the generated token.

### Run agent command

```bash
python 4-langchain-RepoUnderstandingAgent.py
```

### Example output

```bash
Here is a comprehensive overview of the master branch of the Coral-Protocol/coral-server repository:

**Project Purpose &amp; Main Functionality:**
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
Coral Server is a foundation for multi-agent AI systems, enabling agents to communicate, collaborate, and manage conversations through a standardized protocol and set of tools. It is highly extensible and intended as open infrastructure for the &quot;Society of AI Agents.&quot; The project is not yet production-ready but provides a robust starting point for building complex agent-based systems.
```

### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: xinxing@coralprotocol.org

</details>


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

**How to obtain API keys:**

* **OPENAI_API_KEY:**
  Sign up at [platform.openai.com](https://platform.openai.com/), go to “API Keys” under your account, and click “Create new secret key.”

* **GITHUB_ACCESS_TOKEN:**
  Log in to [github.com](https://github.com/), go to **Settings → Developer settings → Personal access tokens**, then “Generate new token,” select the required scopes, and copy the generated token.

### Run agent command

```bash
python 5-langchain-RepoUnitTestAdvisorAgent.py
```

### Example output

```bash
**Coverage Report for `camel/toolkits/new_semantic_scholar_toolkit.py` and its tests**

**Summary of Coverage:**

The file `camel/toolkits/new_semantic_scholar_toolkit.py` defines the `SemanticScholarToolkit` class, which provides five main methods for interacting with the Semantic Scholar API:
1. `fetch_paper_data_title`
2. `fetch_paper_data_id`
3. `fetch_bulk_paper_data`
4. `fetch_recommended_papers`
5. `fetch_author_data`

It also provides a `get_tools` method that returns these as callable tools.

The corresponding test file, `test/toolkits/new_test_semantic_scholar_functions.py`, contains a comprehensive suite of unit tests for all of these methods. The tests use `unittest` and `unittest.mock` to patch `requests.get` and `requests.post`, simulating both successful and error scenarios for each API interaction. Each method is tested for:
- Successful API response (status 200)
- Error handling (non-200 status, exceptions, invalid JSON)
- Correct construction of request parameters and URLs
- Proper handling of optional arguments (like `fields`, `save_to_file`)
- The `get_tools` method is also tested for correct function references.

**Coverage Details:**
- **fetch_paper_data_title**: Tested for both success and error (404) cases.
- **fetch_paper_data_id**: Tested for both success and error (500) cases.
- **fetch_bulk_paper_data**: Tested for both success and error (403) cases.
- **fetch_recommended_papers**: Tested for both success and error (400) cases, including request body validation.
- **fetch_author_data**: Tested for both success and error (404) cases, including request body validation.
- **get_tools**: Tested for correct tool count and function references.

**Missing or Weak Areas:**
- The tests do not verify the actual file writing logic for `save_to_file=True` in `fetch_recommended_papers` and `fetch_author_data`. This is a minor gap, as the file writing is straightforward, but could be covered for completeness.
- Edge cases such as invalid input types (e.g., passing non-list to `ids` or `positive_paper_ids`) are not explicitly tested.
- There is no direct test for the decorator `@MCPServer()`, but this is likely out of scope for unit testing the toolkit's API logic.

**Recommendations:**
- Add tests that set `save_to_file=True` and verify that the expected files are created and contain the correct data (can be done using `unittest.mock` for `open`).
- Optionally, add tests for invalid input types to ensure robust error handling.
- If the `MCPServer` decorator adds critical logic, consider integration tests for its effects.

**Conclusion:**
The unit tests provide thorough coverage of the toolkit's API interaction logic, error handling, and function registration. Only minor improvements are suggested for file output and input validation edge cases. No additional tests are strictly required for the renaming, as the logic and coverage remain unchanged.


### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: xinxing@coralprotocol.org

</details>

---

## [Repo doc consistency checker agent](https://github.com/Coral-Protocol/Coral-RepoDocConsistencyChecker-Agent)

<details>

Repo doc consistency checker agent checks if documentation in a specified repo and branch is up-to-date

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

**How to obtain API keys:**

* **OPENAI_API_KEY:**
  Sign up at [platform.openai.com](https://platform.openai.com/), go to “API Keys” under your account, and click “Create new secret key.”

* **GITHUB_ACCESS_TOKEN:**
  Log in to [github.com](https://github.com/), go to **Settings → Developer settings → Personal access tokens**, then “Generate new token,” select the required scopes, and copy the generated token.

### Run agent command

```bash
python 6-langchain-RepoDocConsistencyCheckerAgent.py
```

### Example output

```bash
**Documentation Consistency Check for PR #2 (branch: 'repo-understanding+unit-test-advice')**

### Changed Files:
1. `4-langchain-RepoUnderstandingAgent.py` (new)
2. `5-langchain-RepoUnitTestAdvisorAgent.py` (new)

### Documentation Coverage:
- The main documentation file is `README.md`.
- The README describes the overall architecture, agent roles, and usage instructions for the system, including launching agents and running unit tests for PRs.
- However, the README **does not mention or document the two new agents**:
    - `RepoUnderstandingAgent` (4-langchain-RepoUnderstandingAgent.py)
    - `RepoUnitTestAdvisorAgent` (5-langchain-RepoUnitTestAdvisorAgent.py)
- There is no section describing their purpose, usage, workflow, or how to launch them.
- The agent roles listed in the README do not include these two new agents, nor are there updated instructions for launching or interacting with them.

### Recommendations:
1. **Update the README.md** to:
    - Add descriptions for `RepoUnderstandingAgent` and `RepoUnitTestAdvisorAgent`, including their responsibilities and how they fit into the system.
    - Update the &quot;Overview of Agents&quot; section to include these new agents.
    - Provide instructions for launching these agents, similar to the other agent scripts.
    - Optionally, add usage examples or scenarios where these agents are involved.

If you need suggested wording or a draft section for the README, let me know!

**Summary:**
The documentation is currently **outdated** with respect to the new agents added in this PR. Please update the README.md as described above.
```

### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: xinxing@coralprotocol.org

</details>

---

# Enterprise

## [PandasAI Agent](https://github.com/Coral-Protocol/Pandas-ai-Agent)

PandasAI Agent lets you ask natural language questions about your Excel or CSV files using a local LLM (e.g., Llama 3.1), just provide the file path and your query to get instant answers.

<details>

### Responsibility

**PandasAI Agent** helps you answer data-related questions about Excel or CSV files using a local LLM (e.g., Llama 3.1) via PandasAI. Simply provide the file path and your natural language question—the agent will query the data and return the answer.

### Details

* Framework: LangChain
* Tools used: PandasAI Tools, Coral MCP Tools
* AI model: OpenAI GPT-4.1 / Llama3.1 via Ollama
* Date added: 04/06/25
* Licence: MIT

### Install Dependencies

Install all required packages:

```bash
pip install langchain langchain_mcp_adapters langchain_openai pandasai python-dotenv anyio
pip install pandas openpyxl
```

### Configure Environment Variables

```bash
export OPENAI_API_KEY=sk-xxx
```

**How to obtain API keys:**

* **OPENAI_API_KEY:**
  Sign up at [platform.openai.com](https://platform.openai.com/), go to “API Keys” under your account, and click “Create new secret key.”

### Run agent command

Make sure Pllama is running in your local machine, then run:

```bash
python 1-langchain-pandasai-agent.py
```

### Example output

```bash
Question: What are the total number of columns in the coral_public_repo_docs.xlsx
Answer: The total number of columns in the coral_public_repo_docs.xlsx is 4.
```

### Creator details

* Name: Xinxing
* Affiliation: Coral Protocol
* Contact: xinxing@coralprotocol.org

</details>

---

# Voice AI Agents

## [Voice Interface Agent](https://github.com/Coral-Protocol/Voice-Interface-Agent)

A real-time voice interface agent that coordinates communication between users and specialized agents. Built on LiveKit with Coral Protocol integration, it enables seamless voice interaction and agent communication.

<details>

### Responsibility

A real-time voice interface agent that coordinates communication between users and specialized agents. Built on LiveKit with Coral Protocol integration, it enables seamless voice interaction and agent communication.

### Details

* Framework: LiveKit Agents
* Tools Used: LiveKit, OpenAI LLM
* AI Model: GPT-4
* Date Added: June 2025
* License: MIT

### Install Dependencies

Install all required packages:

```bash
pip install uv
uv sync
```

### Configure Environment Variables

Copy the example file and update it with your credentials:

```bash
cp env.example .env
```

Required environment variables:

* `LIVEKIT_URL`
* `LIVEKIT_API_KEY`
* `LIVEKIT_API_SECRET`
* `OPENAI_API_KEY`

### Run agent command

Run in terminal (console) mode:

```bash
uv run python main.py console
```

### Agent Capabilities

* **Voice Interface** – Real-time voice communication via voice
* **Agent Routing** – Acts as a central coordinator to connect users with task-specific agents
* **MCP Integration** – Bridges communication using Coral Protocol

### Example Usage

1. Launch the voice interface agent.
2. Speak your query naturally.
3. The system:
   * Captures your voice input
   * Routes the query to the appropriate agent
   * Responds using a clean, real-time voice channel

### Creator Details

* Name: Ahsen Tahir
* Contact: ahsen.t@coralprotocol.org

</details>

## [Medical Office Triage Voice Agent](https://github.com/Coral-Protocol/Medical-Office-Triage-Voice-Agent)

The Medical Office Triage Voice Agent is an intelligent multi-agent voice system that automates patient routing and support in medical office environments. It uses real-time voice processing to understand patient needs and seamlessly transfers them between specialized departments (Triage, Support, and Billing) while maintaining conversation context.

<details>

### Responsibility

The Medical Office Triage Voice Agent is an intelligent multi-agent voice system that automates patient routing and support in medical office environments. It uses real-time voice processing to understand patient needs and seamlessly transfers them between specialized departments (Triage, Support, and Billing) while maintaining conversation context. The system leverages Deepgram for speech-to-text, Cartesia for text-to-speech, OpenAI for natural language understanding, and LiveKit for real-time communication with noise cancellation capabilities.

### Details

* Framework: LiveKit Agents
* Tools used: Deepgram STT, Cartesia TTS, OpenAI LLM, Silero VAD, LiveKit Plugins
* AI model: GPT-4o-mini
* Date added: June 2025
* License: MIT
* Original source: [Medical Office Triage](https://github.com/livekit-examples/python-agents-examples/tree/main/complex-agents/medical_office_triage)

### Install Dependencies

Install all required packages:

```bash
pip install uv
uv sync
```

### Configure Environment Variables

Copy example environment file:

```bash
cp env.example .env
```

Edit the `.env` file and add your API keys:

* LiveKit API key and secret (get from LiveKit Console)
* OpenAI API key (get from OpenAI Console)
* Deepgram API key (get from Deepgram Console)
* Cartesia API key (get from Cartesia Console)

### Run agent command

```bash
uv run triage.py console
```

### Agent Capabilities

* **Triage Agent**: Initial patient intake, determines appropriate department routing
* **Support Agent**: Handles medical services, appointments, and general patient support inquiries
* **Billing Agent**: Manages insurance inquiries, payment questions, and billing support

### Technical Features

* **Multi-Agent Voice System**: Three specialized AI agents working seamlessly together
* **Real-time Voice Processing**: Deepgram speech-to-text, Cartesia text-to-speech, OpenAI language understanding
* **Intelligent Routing**: Automatic patient transfer between departments based on conversation analysis

### Example Usage

1. **Start the application using the console command** - The system initializes with all three agents ready
2. **Begin speaking when you hear the system is ready** - You'll be connected to the Triage Agent first
3. **Triage Agent interaction** - The Triage Agent will:
   * Listen to your initial request or concern
   * Ask clarifying questions about your medical office needs
   * Determine whether you need appointment scheduling, medical support, or billing assistance
   * Route you to the appropriate specialist agent based on your needs
4. **Automatic transfer to specialist agents**:
   * **Support Agent** - If you need:
     * Medical appointment scheduling
     * General patient support inquiries
     * Information about medical services
     * Health-related questions and guidance
   * **Billing Agent** - If you need:
     * Insurance verification and claims
     * Payment processing and billing questions
     * Cost estimates for procedures
     * Financial assistance programs
5. **Continue the conversation naturally** - Once transferred:
   * The specialist agent has full context of your previous conversation
   * You can ask follow-up questions specific to that department
   * The agent can transfer you back to Triage or to another specialist if needed
   * All conversation history is preserved throughout transfers

### Creator Details

* Name: Ahsen Tahir
* Contact: ahsen.t@coralprotocol.org

</details>

## [Restaurant Voice Agent System](https://github.com/Coral-Protocol/Restuarant-Voice-Agent)

A multi-agent voice conversation system for restaurants that handles reservations, takeaway orders, and checkout through natural voice interactions. Features four specialized AI agents that seamlessly transfer conversations while maintaining context.

<details>

### Responsibility

A multi-agent voice conversation system for restaurants that handles reservations, takeaway orders, and checkout through natural voice interactions. Features four specialized AI agents that seamlessly transfer conversations while maintaining context.

### Details

* Framework: LiveKit Agents
* Tools Used: Deepgram STT, Cartesia TTS, OpenAI LLM, Silero VAD
* AI Model: GPT-4
* Date Added: January 2025
* License: MIT
* Original Source: [Restaurant Voice Agent System](https://github.com/livekit/agents/blob/main/examples/voice_agents/restaurant_agent.py)

### Install Dependencies

Install all required packages:

```bash
pip install uv
uv sync
```

### Configure Environment Variables

Copy the example file and add your API keys:

```bash
cp env.example .env
```

Update `.env` with:

* `LIVEKIT_URL`
* `LIVEKIT_API_KEY`
* `LIVEKIT_API_SECRET`
* `OPENAI_API_KEY`
* `DEEPGRAM_API_KEY`
* `CARTESIA_API_KEY`

### Run agent command

```bash
uv run python main.py console
```

### Agent System

* **🏪 Greeter Agent**: Restaurant receptionist that welcomes customers, presents menu (Pizza $10, Salad $5, Ice Cream $3, Coffee $2), and routes to specialized agents.
* **📅 Reservation Agent**: Handles dining reservations - collects time, customer name, and phone number.
* **🥡 Takeaway Agent**: Processes food orders - takes orders from menu, clarifies requests, confirms details.
* **💳 Checkout Agent**: Handles payments - calculates expenses, collects contact info and credit card details.

### Usage Examples

**Making a Reservation:**

1. Say: "I'd like to make a reservation"
2. Provide preferred time, name, and phone
3. Confirm details

**Ordering Takeaway:**

1. Say: "I want to order food"
2. Place order from menu
3. Provide payment information
4. Complete transaction

### Creator Details

* Name: Ahsen Tahir
* Contact: ahsen.t@coralprotocol.org

</details>

## [Voice French Agent](https://github.com/Coral-Protocol/Voice-French-Agent)

A real-time multilingual voice assistant that listens to English speech and responds fluently in French. It uses Deepgram for speech-to-text, OpenAI for translation, ElevenLabs for French voice synthesis, and LiveKit for real-time communication with built-in noise cancellation.

<details>

### Responsibility

A real-time multilingual voice assistant that listens to English speech and responds fluently in French. It uses Deepgram for speech-to-text, OpenAI for translation, ElevenLabs for French voice synthesis, and LiveKit for real-time communication with built-in noise cancellation.

### Details

* Framework: LiveKit Agents
* Tools Used: Deepgram STT, ElevenLabs TTS, OpenAI LLM, LiveKit Plugins
* AI Model: GPT-4
* Date Added: June 2025
* License: MIT
* Original Source: [Voice French Agent](https://github.com/livekit-examples/python-agents-examples/blob/main/translators/pipeline_translator.py)

### Install Dependencies

Install all required packages:

```bash
pip install uv
uv sync
```

### Configure Environment Variables

Copy the example file and add your API keys:

```bash
cp env.example .env
```

Update `.env` with:

* `LIVEKIT_URL`
* `LIVEKIT_API_KEY`
* `LIVEKIT_API_SECRET`
* `OPENAI_API_KEY`
* `DEEPGRAM_API_KEY`
* `ELEVENLABS_API_KEY`

### Run agent command

Start the agent with voice input/output:

```bash
uv run python main.py console
```

### Agent Capabilities

* **English Speech Recognition** – via Deepgram
* **AI Translation to French** – powered by OpenAI
* **French Voice Output** – using ElevenLabs
* **Noise Cancellation** – with LiveKit plugins

### Example Usage

1. Start the agent.
2. Speak in English.
3. The agent:
   * Transcribes your speech.
   * Translates to French.
   * Responds in natural French voice.

### Creator Details

* Name: Ahsen Tahir
* Contact: ahsen.t@coralprotocol.org

</details>

---

# Know More 🐙  
Learn more about the Coral Protocol at [Coral Documentation](https://docs.coralprotocol.org/CoralDoc/Introduction/WhatisCoralProtocol).
