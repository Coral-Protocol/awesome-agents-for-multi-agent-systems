# Spreadsheet analysis along with GMAIL supported by Voice Commands with LangChain, PydanticAI and LiveKit

This guide demonstrates a multi-agent system for spreadsheet analysis, Gmail integration, and voice command processing, built using Coral Protocol. The system supports multiagents running on multiple frameworks- [LiveKit](https://github.com/livekit/livekit), [LangChain](https://github.com/langchain-ai/langchain) and [PydanticAI](https://github.com/pydantic/pydantic-ai). It enables automated spreadsheet data processing, email drafting and sending via Gmail, and voice command recognition for hands-free operation.

![multiagent-image](https://github.com/Coral-Protocol/awesome-agents-for-multi-agent-systems/blob/main/images/Multi-agent_System-Gmail_Integration_with_Voice_Command_Support.png)

### Introduction

- The system consists of three specialized agents that collaborate to process spreadsheet data, interact with Gmail, and handle voice commands. The [Voice Interface Agent](https://github.com/Coral-Protocol/Coral-VoiceInterface-Agent), built with LiveKit, serves as the central coordinator, interpreting user instructions (text or voice), managing the workflow, and orchestrating the other agents. The [Pandas Agent](https://github.com/Coral-Protocol/Coral-Pandas-Agent), powered by LangChain, handles spreadsheet data processing, including loading, analyzing, and generating reports from CSV or Excel files with validated data structures. The [ACIdev agent](https://github.com/Coral-Protocol/Coral-AciDevMCP-Agent/tree/pydantic-ai), utilizing PydaticAI, processes voice commands, converts them to text, and triggers appropriate actions, such as generating emails or querying spreadsheet data. The system integrates with Gmail APIs to draft and send emails based on analysis results or user commands.

- In this example we are using the Titanic spreadsheet: `https://raw.githubusercontent.com/pandas-dev/pandas/main/doc/data/titanic.cs`.

- Agents: [Voice Interface Agent](https://github.com/Coral-Protocol/Coral-VoiceInterface-Agent) | [Pandas Agent](https://github.com/Coral-Protocol/Coral-Pandas-Agent) | [ACIdev agent](https://github.com/Coral-Protocol/Coral-AciDevMCP-Agent/tree/pydantic-ai)

- [Demo video](https://drive.google.com/file/d/1-VG3Kgld_AdSJx4suWBZ-x2K6QdGaCot/view)

### Outline

- **Setup Coral Server and Coral Studio**  
  Step-by-step guide to install and run Coral Server with necessary dependencies (Java).

- **Setup the Agents**  
  Instructions to install and configure the agents.

- **Run the Agents**  
  Available options to run agents:
  - Dev Mode (terminal-based) for easier debugging  

- **Example**  
  Sample input and output to get results.

### How to run step by step

### 1. Setup Coral Server and Coral Studio

<details>

- To setup the [Coral Server](https://github.com/Coral-Protocol/coral-server) and [Coral Studio UI](https://github.com/Coral-Protocol/coral-studio), follow the steps given in repository to install.

- In order to test if both are working, open the same instance in two terminals and run both simultaneously.

```bash
# run studio
yarn dev
```
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

# Allow port for eternal access
sudo ufw allow 5173

```

Run Coral Studio

```bash

yarn dev

```

</details>

</details>

### 2. Setup the Agents


<details>  

- Terminate the Coral Server from above and start below steps.
- In this example, we are using the agents: [Coral Voice Interface Agent](https://github.com/Coral-Protocol/Coral-VoiceInterface-Agent) , [Coral Pandas Agent](https://github.com/Coral-Protocol/Coral-Pandas-Agent) and [Coral ACIdev agent](https://github.com/Coral-Protocol/Coral-AciDevMCP-Agent/tree/pydantic-ai).  
- Please click on the link and set up the agents by following the setup instructions in the repository.  
- Check the output below to see how the terminal will look after succesfull installation, keep in mind the directory you are at while doing `uv sync`.


</details>

### 3. Run the Agents

<details>

<summary>You can run the agents in dev mode via terminal.</summary>

#### 1. Dev Mode

<details>

- The Dev Mode allows the Coral Server and all agents to be seaprately running on each terminal without UI support.  

- Ensure that the [Coral Server](https://github.com/Coral-Protocol/coral-server) is running on your system and run below commands in separate terminals.

- Ensure that you have setup the `.env` file with required keys.  

Run the Voice Interface Agent

```bash
# cd to directory
cd Coral-VoiceInterface-Agent

# Run the agent using `uv`:
uv run  main.py console
```

Run the Pandas Agent

```bash
# cd to directory
cd Coral-Pandas-Agent

# Run the agent using `uv`:
uv run main.py
```
Run the ACIdev agent 
```bash
#cd to the directory
cd Coral-AciDevMCP-Agent

#Run the agent using 'uv'
uv run main.py
```

</details>

</details>

### 4. Example

<details>

```bash
You have to give a voice input like this
# Input:
ask the pandas agent to describe me the coloums for 'titanic.csv' 

#Output:
The agent will respond back with the column description.

#Input:
then you can ask it to send this information to the ACIdev agent and email to xyz@gmail.com with the subject of Data Description.

#Output:
The email will be sent.

```

</details>

</details>


### Where to find support 

If you have any questions about anything you can join our discord here, and put something in the dev support channel, if you beleivie it to be a bug or a feate that you want you can add it as a github issue https://discord.gg/HaTjdMGBHc

