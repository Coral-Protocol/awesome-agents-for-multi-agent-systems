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

The MCP Tools interface will show the coral-interface server with various functions available including list_agents, create_thread, add_participant, remove_participant, close_thread, send_message, and wait_for_mentions.

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