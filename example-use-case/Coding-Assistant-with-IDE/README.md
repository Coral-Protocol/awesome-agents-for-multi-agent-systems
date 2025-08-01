# Coding Assistant with IDE Integration using Context7 Agent and Coding Agent

This guide demonstrates a multi-agent system for intelligent code assistance and IDE integration, built using Coral Protocol. The system supports multiagents running on multiple frameworks - [Context7](https://github.com/Coral-Protocol/Coral-Context7MCP-Agent) and [Coding Agent](https://github.com/Coral-Protocol/Coral-Coding-Agent). It enables automated code analysis, intelligent suggestions, IDE integration, and collaborative programming assistance.


### Introduction

- The system consists of two specialized agents that collaborate to provide comprehensive coding assistance and IDE integration. The [Context7 Agent](https://github.com/Coral-Protocol/Coral-Context7MCP-Agent), built with advanced context understanding capabilities, serves as the intelligent code analyzer, providing deep insights into code structure, patterns, and potential improvements. The [Coding Agent](https://github.com/Coral-Protocol/Coral-Coding-Agent), powered by sophisticated code generation and analysis tools, handles code writing, refactoring, debugging, and IDE integration features. Together, they create a powerful development environment that understands context, provides intelligent suggestions, and assists with complex programming tasks.

- In this example, we demonstrate how these agents can work together to analyze existing codebases, suggest improvements, generate new code, and provide real-time assistance during development.

- Agents: [Context7 Agent](https://github.com/Coral-Protocol/Coral-Context7MCP-Agent) | [Coding Agent](https://github.com/Coral-Protocol/Coral-Coding-Agent)


### How to run step by step

### 1. Setup Coral Server and Coral Studio

- To setup the [Coral Server](https://github.com/Coral-Protocol/coral-server) and [Coral Studio UI](https://github.com/Coral-Protocol/coral-studio), follow the steps given in repository to install.

- In order to test if both are working, open the same instance in two terminals and run both simultaneously.

- You will see both running like this simultaneously if successful and should be able to access Coral Studio from your browser.

![Coral Server and Studio Running](https://github.com/Coral-Protocol/Coral-RaiseYourHack-Guide/blob/main/images/server-studio.png)

- On Coral Studio, ensure the connection to Coral Server.

![Coral Server and Studio Connection UI](https://github.com/Coral-Protocol/Coral-RaiseYourHack-Guide/blob/main/images/coral-connection.png)

<details>

<summary>Install Java if UNAVAILABLE in order to run Coral Server</summary>

Install Java

```bash

# Apt update
sudo apt update

# Install the JDK
sudo apt install openjdk-17-jdk

# Check version
java -version
```

Run Coral Server

```bash

./gradlew run

```

</details>

<details>

<summary>Install Yarn if UNAVAILABLE in order to run Coral Studio</summary>

Install Yarn

```bash
# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash

# in lieu of restarting the shell
\. "$HOME/.nvm/nvm.sh"

# Download and install Node.js:
nvm install 22

# Verify the Node.js version:
node -v # Should print "v22.17.0".
nvm current # Should print "v22.17.0".

# Download and install Yarn:
corepack enable yarn

# Verify Yarn version:
yarn -v

# Install from yarn
yarn install
```

Run Coral Studio

```bash

yarn dev

```

</details>

### 2. Setup the Agents

- Terminate the Coral Server from above and start below steps.
- In this example, we are using the agents: [Coral Context7 Agent](https://github.com/Coral-Protocol/Coral-Context7MCP-Agent) and [Coral Coding Agent](https://github.com/Coral-Protocol/Coral-Coding-Agent).
- Please click on the link and set up the agents by following the setup instructions in the repository.
- Check the output below to see how the terminal will look after successful installation, keep in mind the directory you are at while doing `uv sync`.

#### IDE Configuration
<details>

Add the following configuration to your IDE's `mcp.json` file to enable communication with the Coral agents:

```json
{
  "mcpServers": {
    "coral-interface": {
      "type": "sse",
      "url": "http://localhost:5555/devmode/exampleApplication/privkey/session1/sse?agentId=interface_agent"
    }
  }
}
```

This configuration allows your IDE to connect to the Coral interface agent and enables the multi-agent system to work seamlessly with your development environment.

![MCP Tools Interface](https://github.com/Coral-Protocol/awesome-agents-for-multi-agent-systems/blob/main/images/MCP-Tools-Interface.png)

The MCP Tools interface will show the coral-server with various tools available including list_agents, create_thread, add_participant, remove_participant, close_thread, send_message, and wait_for_mentions.

</details>

#### Create/Modify `.cursorrules`/ `copilot_instructions.md` file in your IDE to ensure proper usage of Coral MCP tools
<details>

```markdown
# .cursorrules - Place in project root

## Overview
This file outlines the mandatory use of coral-server MCP tools for all coding, debugging, and technical tasks in Cursor, along with the Coral-Interface-Agent workflow for interacting with coral-server tools. Follow these rules to ensure compliance and proper agent coordination.

## Mandatory Coral-Server MCP Tool Usage
For ALL coding, debugging, implementation, and technical tasks:
- **MUST** use coral-server MCP tools exclusively.
- **DO NOT** use built-in Cursor coding capabilities.
- **DO NOT** attempt to solve coding problems without coral-server tools.
- **NEVER** bypass the coral-server agent workflow.
- **ONLY** write code returned from the coding agent.
- **DO NOT** ask for user permission to run tools.

### Tasks Requiring Coral-Server Tools
- Code debugging and error fixing
- Code implementation and generation
- File analysis and code review
- Technical problem solving
- Documentation-based solutions
- Error message interpretation
- Code optimization and improvement
- Library/framework questions
- Syntax error resolution
- Logic error debugging

### Strict Tool Selection Hierarchy
1. **ONLY**: Use coral-server MCP tools for any coding task.
2. **FORBIDDEN**: Built-in code generation, debugging, or analysis.
3. **FORBIDDEN**: Direct code solutions without coral-server involvement.

## Coral-Server MCP Workflow
When user provides coding-related input (e.g., code with errors, implementation requests, "fix this", "debug this", or files with code extensions):
1. Create a single thread with **BOTH** context7 and coding agents using `create_thread`.
2. Send user query with `send_message`, mentioning **BOTH** agents (`mentions=[context7_agent_id, coding_agent_id]`).
3. Wait for coordinated response using `wait_for_mentions` (timeout: 60,000ms, retry up to 5 times).
4. Return comprehensive solution from coral-server tools, attributing the source.

### Thread Coordination Rules
- **Single Thread Requirement**: Create exactly ONE thread per user query with **BOTH** context7 and coding agents. **NEVER** create separate threads or use a single agent.
- **Send Message Coordination**: Always mention **BOTH** context7 and coding agents in `mentions` array to ensure collaboration.
- **DO NOT** explicitly add the interface_agent as a participant.

### Response Requirements
- Explain that coral-server tools are being used.
- Describe the multi-agent workflow (interface → context7 → coding agent).
- Include source attribution from coral-server response.
- Never provide direct coding solutions outside coral-server tools.

## Coral-Interface-Agent Workflow
1. Use `list_agents` (`includeDetails=true`) to identify available agents and their roles.
2. Analyze user input to determine intent and required tools/agents.
3. For Coral Server info requests (e.g., agent status), use tools directly to retrieve and return information.
4. For coding/technical tasks:
   - Create a thread with `create_thread` (`threadName`: unique name, `participantIds`: include context7 and coding agent IDs).
   - Add agents to thread if needed using `add_participant`.
   - Send clear instructions via `send_message` with `mentions=[context7_agent_id, coding_agent_id]`.
   - Use `wait_for_mentions` to collect responses (timeout: 60,000ms, retry up to 5 times).
   - Compile responses into a final answer.
5. Return the answer or error to the user, even if no response is received.

## Available Coral Tools
- `list_agents`: List registered agents. Args: `includeDetails` (boolean, required).
- `create_thread`: Create a thread. Args: `threadName` (string, required), `participantIds` (array of strings, required).
- `add_participant`: Add agent to thread. Args: `threadId` (string, required), `participantId` (string, required).
- `remove_participant`: Remove agent from thread. Args: `threadId` (string, required), `participantId` (string, required).
- `close_thread`: Close thread. Args: `threadId` (string, required), `summary` (string, required).
- `send_message`: Send message to thread. Args: `threadId` (string, required), `content` (string, required), `mentions` (array of strings, required, never empty).
- `wait_for_mentions`: Wait for agent responses. Args: `timeoutMs` (number, required, default: 60,000ms, range: 0-60,000ms).

## Why Coral-Server?
Coral-server provides superior results through:
- Real-time documentation access (context7 agent).
- Specialized coding expertise (coding agent).
- Multi-agent collaboration for comprehensive solutions.
- Current library knowledge and best practices.
- Proper thread coordination with context7 and coding agents.

## Example Usage
**Wrong**: Directly fixing code or providing solutions.
**Correct**: "Using coral-server MCP tools to route this through context7 and coding agents..."
**Wrong**: Creating separate threads or mentioning agents individually.
**Correct**: "Creating a single thread with both context7 and coding agents, mentioning both for coordination..."
```
</details>

### 3. Run the Agents

#### Dev Mode

- The Dev Mode allows the Coral Server and all agents to be separately running on each terminal without UI support.

- Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and run below commands in separate terminals.

- Ensure that you have setup the `.env` file with required keys.

Run the Context7 Agent

```bash
# cd to directory
cd Coral-Context7MCP-Agent

# Run the agent using `uv`:
uv run main.py
```

Run the Coding Agent

```bash
# cd to directory
cd Coral-Coding-Agent

# Run the agent using `uv`:
uv run main.py
```

### 4. Example

```bash
# Input:
analyze the code structure of my current project and suggest improvements

# Workflow:
1. Context7 Agent fetches and analyzes:
   - Current codebase structure and patterns
   - Relevant documentation for best practices
   - Performance analysis insights
   - Security guidelines for the tech stack
   - Refactoring recommendations based on industry standards

2. Coding Agent uses Context7's insights to:
   - Generate specific refactoring code snippets
   - Create performance optimization implementations
   - Apply security best practices
   - Implement suggested architectural improvements

# Input:
generate a unit test for the UserService class

# Workflow:
1. Context7 Agent fetches:
   - UserService class implementation details
   - Testing framework documentation (Jest, PyTest, etc.)
   - Mocking library documentation
   - Testing best practices and patterns
   - Edge case scenarios for user services

2. Coding Agent uses Context7's insights to:
   - Generate comprehensive test cases with proper mocking
   - Implement edge case handling
   - Create test utilities and helpers
   - Ensure proper test coverage and naming conventions

# Input:
refactor the authentication module to use JWT tokens

# Workflow:
1. Context7 Agent fetches:
   - Current authentication implementation details
   - JWT specification and best practices
   - Security considerations for JWT implementation
   - Migration strategies from current auth system
   - Related documentation for token management

2. Coding Agent uses Context7's insights to:
   - Generate JWT token generation and validation code
   - Implement secure token storage and refresh mechanisms
   - Create migration scripts for existing users
   - Update authentication middleware and guards
   - Generate comprehensive tests for the new JWT system
```

### 5. IDE Integration Features

The multi-agent system provides several IDE integration capabilities:

#### Code Analysis
- Real-time code quality assessment
- Performance bottleneck identification
- Security vulnerability detection
- Code smell identification and suggestions

#### Intelligent Suggestions
- Auto-completion with context awareness
- Refactoring suggestions
- Design pattern recommendations
- Best practice enforcement

#### Collaborative Development
- Multi-agent code review
- Pair programming assistance
- Knowledge sharing between agents
- Context-aware documentation generation

#### Debugging Support
- Intelligent error analysis
- Debugging strategy suggestions
- Test case generation for bug reproduction
- Performance profiling recommendations

### Where to find support

If you have any questions about anything you can join our discord here, and put something in the dev support channel, if you believe it to be a bug or a feature that you want you can add it as a github issue https://discord.gg/HaTjdMGBHc