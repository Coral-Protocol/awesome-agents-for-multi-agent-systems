# Software Testing Multiagents with LangChain, Camel, and CrewAI

This guide demonstrates a multi-agent software testing system built using Coral Protocol, supporting agents from three different frameworks [LangChain](https://github.com/langchain-ai/langchain), [Camel](https://github.com/camel-ai/camel), and [CrewAI](https://github.com/crewAIInc/crewAI). The system enables automatic understanding of codebases, pull request testing, test coverage analysis, and documentation consistency checking in any compatible GitHub repository.

![multiagent-image](https://github.com/Coral-Protocol/awesome-agents-for-multi-agent-systems/blob/main/images/Software_Testing_Multiagents.png)

### Introduction

- The system is composed of four specialized agents that work together to streamline GitHub pull request processing. The [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent), built with LangChain, acts as the central coordinator, accepting user instructions, managing the workflow, and orchestrating the other agents. The [GitClone Agent](https://github.com/Coral-Protocol/Coral-GitClone-Agent), powered by Crew AI, handles cloning the specified GitHub repository and checking out the relevant pull request branch. The [CodeDiffReview Agent](https://github.com/Coral-Protocol/Coral-CodeDiffReview-Agent), utilizing Camel, analyzes the pull request diff, identifies modified functions, maps them to corresponding tests, and locates associated test files. Lastly, the [UnitTestRunner Agent](https://github.com/Coral-Protocol/Coral-UnitTestRunner-Agent), also based on LangChain, executes designated unit tests using pytest and provides structured results, ensuring an efficient and automated review process.

- Agents: [Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent) | [GitClone Agent](https://github.com/Coral-Protocol/Coral-GitClone-Agent) | [CodeDiffReview Agent](https://github.com/Coral-Protocol/Coral-CodeDiffReview-Agent) | [UnitTestRunner Agent](https://github.com/Coral-Protocol/Coral-UnitTestRunner-Agent)

- Checkout demo video below.  

[![Demo Video](https://github.com/Coral-Protocol/awesome-agents-for-multi-agent-systems/blob/main/images/Software_Testing_Multiagents_Video2.png)](https://drive.google.com/file/d/1PyVQd8Z7rfqbokZ6hsp8m_2IMI29QH7B/view?usp=drive_link)

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

- Terminate the Coral Server and Coral Studio connections from above and start below steps.
- In this example, we are using the agents: [Coral Interface Agent](https://github.com/Coral-Protocol/Coral-Interface-Agent), [GitClone Agent](https://github.com/Coral-Protocol/Coral-GitClone-Agent), [CodeDiffReview Agent](https://github.com/Coral-Protocol/Coral-CodeDiffReview-Agent) and [UnitTestRunner Agent](https://github.com/Coral-Protocol/Coral-UnitTestRunner-Agent).  
- Please click on the link and set up the agents by following the setup instructions in the repository.  
- Check the output below to see how the terminal will look after succesfull installation, keep in mind the directory you are at while doing `uv sync`.


### 3. Run the Agents

#### Executable Mode

- The Executable Mode is part of the Coral Protocol Orchestrator which works with [Coral Studio UI](https://github.com/Coral-Protocol/coral-studio).  

- Checkout: [How to Build a Multi-Agent System with Awesome Open Source Agents using Coral Protocol](https://github.com/Coral-Protocol/existing-agent-sessions-tutorial-private-temp).  

- Update the file: `coral-server/src/main/resources/application.yaml` with the details below. 

```bash
# replace ${PROJECT_DIR} with YOUR/PROJECT/DIRECTORY

applications:
  - id: "app"
    name: "Default Application"
    description: "Default application for testing"
    privacyKeys:
      - "default-key"
      - "public"
      - "priv"

registry:
  interface:
    options:
      - name: "API_KEY"
        type: "string"
        description: "API key for the service"
    runtime:
      type: "executable"
      command: ["bash", "-c", "${PROJECT_DIR}/Coral-Interface-Agent/run_agent.sh main.py"]
      environment:
        - name: "API_KEY"
          from: "API_KEY"
        - name: "MODEL_NAME"
          value: "gpt-4.1"
        - name: "MODEL_PROVIDER"
          value: "openai"
        - name: "MODEL_TOKEN"
          value: "16000"
        - name: "MODEL_TEMPERATURE"
          value: "0.3"

  GitClone:
    options:
      - name: "API_KEY"
        type: "string"
        description: "API key for the service"
    runtime:
      type: "executable"
      command: ["bash", "-c", "${PROJECT_DIR}/Coral-GitClone-Agent/run_agent.sh main.py"]
      environment:
        - name: "API_KEY"
          from: "API_KEY"
        - name: "MODEL_NAME"
          value: "openai/gpt-4.1-mini"
        - name: "MODEL_TOKEN"
          value: "16000"
        - name: "MODEL_TEMPERATURE"
          value: "0.3"

  CodeDiff:
    options:
      - name: "API_KEY"
        type: "string"
        description: "API key for the service"
      - name: "GITHUB_ACCESS_TOKEN"
        type: "string"
        description: "key for the github service" 
    runtime:
      type: "executable"
      command: ["bash", "-c", "${PROJECT_DIR}/Coral-CodeDiffReview-Agent/run_agent.sh main.py"]
      environment:
        - name: "API_KEY"
          from: "API_KEY"
        - name: "GITHUB_ACCESS_TOKEN"
          from: "GITHUB_ACCESS_TOKEN"
        - name: "MODEL_NAME"
          value: "gpt-4.1-mini"
        - name: "MODEL_PROVIDER"
          value: "openai"
        - name: "MODEL_TOKEN"
          value: "16000"
        - name: "MODEL_TEMPERATURE"
          value: "0.3"

  UnitTest:
    options:
      - name: "API_KEY"
        type: "string"
        description: "API key for the service"
    runtime:
      type: "executable"
      command: ["bash", "-c", "${PROJECT_DIR}/Coral-UnitTestRunner-Agent/run_agent.sh main.py"]
      environment:
        - name: "API_KEY"
          from: "API_KEY"
        - name: "MODEL_NAME"
          value: "gpt-4.1-mini"
        - name: "MODEL_PROVIDER"
          value: "openai"
        - name: "MODEL_TOKEN"
          value: "16000"
        - name: "MODEL_TEMPERATURE"
          value: "0.3"
```

- Run the [Coral Server](https://github.com/Coral-Protocol/coral-server) and [Coral Studio](https://github.com/Coral-Protocol/coral-studio). 

- You do not need to set up the `.env` in the project directory for running in this mode; it will be captured through the variables below.  

- After the agents are loaded properly, you will see "4 agents" connected. Proceed ahead with "Select Session", add the agents, api key and esure to add both the Custom Tools to the Interface Agent.



### 5. Example


```bash
# Input:
Question:

# Output:
Answer: 
```


### Where to find support 

If you have any questions about anything you can join our discord here, and put something in the dev support channel, if you beleivie it to be a bug or a feate that you want you can add it as a github issue [Discord](https://discord.com/invite/Xjm892dtt3)

