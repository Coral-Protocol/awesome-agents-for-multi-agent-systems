# Canva-Design-Automation-with-Deep-Research 

This guide demonstrates a multi-agent system for automated design creation with deep research capabilities, built using Coral Protocol. The system supports multiagents running on multiple frameworks - [LangChain](https://github.com/langchain-ai/langchain) and other modern AI frameworks. It enables automated design creation in Canva, deep research integration, and intelligent interface coordination for seamless operation.

### Introduction

- The system consists of three specialized agents that collaborate to create designs and conduct research. The [Coral Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) serves as the central coordinator, interpreting user instructions, managing the workflow, and orchestrating the other agents. The [Canva Dev MCP Agent](https://github.com/Coral-Protocol/Coral-CanvaDevMCP-Agent), powered by the Canva Developer Platform, handles design creation in Canva, including creating, modifying, and exporting designs. The [Open Deep Research Agent](https://github.com/Coral-Protocol/Coral-OpenDeepResearch-Agent) conducts comprehensive research to gather relevant information and insights that can be incorporated into the designs.

- Agents: [Coral Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) | [Canva Dev MCP Agent](https://github.com/Coral-Protocol/Coral-CanvaDevMCP-Agent) | [Open Deep Research Agent](https://github.com/Coral-Protocol/Coral-OpenDeepResearch-Agent)
- [Demo](https://getrapidemo.com/videos/4054fabf-c87a-4a3b-8a3b-051e521e6873)

### How to run step by step

### 1. Setup Coral Server and Coral Studio

- To setup the [Coral Server](https://github.com/Coral-Protocol/coral-server) and [Coral Studio UI](https://github.com/Coral-Protocol/coral-studio), follow the steps given in repository to install.

- In order to test if both are working, open the same instance in two terminals and run both simultaneously.

- You will see both running like this simultaneously if succesful and should be able to access Coral Studio from your browser.

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
- In this example, we are using the agents: [Coral Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent), [Canva Dev MCP Agent](https://github.com/Coral-Protocol/Coral-CanvaDevMCP-Agent) and [Open Deep Research Agent](https://github.com/Coral-Protocol/Coral-OpenDeepResearch-Agent).
- Please click on the link and set up the agents by following the setup instructions in the repository.  
- Check the output below to see how the terminal will look after successful installation, keep in mind the directory you are at while doing `uv sync`.


### 3. Run the Agents


<summary>You can run the agents in dev mode via terminal.</summary>

#### 1. Dev Mode

<details>

- The Dev Mode allows the Coral Server and all agents to be separately running on each terminal without UI support.  

- Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and run below commands in separate terminals.

- Ensure that you have setup the `.env` file with required keys.  

Run the Interface Agent

```bash
# cd to directory
cd Coral-Interface-Agent

# Run the agent using `uv`:
uv run main.py
```

Run the Canva Dev MCP Agent

```bash
# cd to directory
cd Coral-CanvaDevMCP-Agent

# Run the agent using `uv`:
uv run main.py
```

Run the Open Deep Research Agent
```bash
# cd to directory
cd Coral-OpenDeepResearch-Agent

# Run the agent using `uv`:
uv run main.py
```

</details>


### 4. Example


```bash
# Input:
Request deep research on AI agents

# Output:
The Open Deep Research Agent initiates comprehensive research

# Input:
Create a Canva presentation using the research findings

# Output:
1. Interface Agent:
   - Processes research data
   - Initiates communication with Canva Agent

2. Canva Dev MCP Agent:
   - Prompts for design preferences
   - Creates presentation with research content
   - Provides Canva design URLs
```


### Where to find support 

If you have any questions about anything you can join our discord here, and put something in the dev support channel, if you believe it to be a bug or a feature that you want you can add it as a github issue https://discord.gg/HaTjdMGBHc

