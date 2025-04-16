<div align="center">

<img src="https://github.com/UnisonAI/UnisonAI/blob/main/assets/UnisonAI_Banner.jpg" alt="UnisonAI Banner" width="90%"/>

<h1><b>UnisonAI: The Multi-Agent Framework for Modern AI Collaboration</b></h1>
<p>
  <i>Build, orchestrate, and scale intelligent agents—solo or in teams—using your favorite LLMs.</i>
</p>

<p>
  <a href="https://github.com/UnisonAI/UnisonAI/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/UnisonAI/UnisonAI?style=for-the-badge" alt="License: Apache 2.0"/>
  </a>
  <a href="https://github.com/UnisonAI/UnisonAI/stargazers">
    <img src="https://img.shields.io/github/stars/UnisonAI/UnisonAI?style=for-the-badge" alt="GitHub Repo stars"/>
  </a>
  <a href="https://github.com/UnisonAI/UnisonAI/network/members">
    <img src="https://img.shields.io/github/forks/UnisonAI/UnisonAI?style=for-the-badge" alt="GitHub forks"/>
  </a>
  <a href="https://github.com/UnisonAI/UnisonAI/issues">
    <img src="https://img.shields.io/github/issues/UnisonAI/UnisonAI?style=for-the-badge" alt="GitHub issues"/>
  </a>
  <a href="https://github.com/UnisonAI/UnisonAI/commits/main">
    <img src="https://img.shields.io/github/last-commit/UnisonAI/UnisonAI?style=for-the-badge" alt="GitHub last commit"/>
  </a>
</p>

</div>

---

<div align="center">

### 🌟 <b>UnisonAI: Orchestrate AI Agents with Power & Simplicity</b> 🌟
<b>Compose teams of LLM-powered agents, extend with custom tools, and unlock collaborative AI automation.</b>
</div>

<br/>

<p align="center">
  <a href="#-overview">Overview</a> •
  <a href="#-why-unisonai">Why UnisonAI?</a> •
  <a href="#️-installation">Installation</a> •
  <a href="#-core-components">Core Components</a> •
  <a href="#-parameter-reference-tables">Parameter Reference Tables</a> •
  <a href="#-usage-examples">Usage Examples</a> •
  <a href="#-faq">FAQ</a> •
  <a href="#-contributing-and-license">Contributing and License</a>
</p>


---

<div align="center">

<img src="https://img.shields.io/badge/Python-%3E=3.10,%3C3.13-blue?style=flat-square" alt="Python Version"/>
<img src="https://img.shields.io/badge/LLM%20Support-Mixtral%2C%20Grok%2C%20Gemini%2C%20OpenAI%2C%20Cohere%20%26%20more-orange?style=flat-square" alt="LLM Support"/>
<img src="https://img.shields.io/badge/architecture-Single%20Agent%20%2F%20Clan%20(Multi--Agent)-purple?style=flat-square" alt="Architecture"/>

</div>

---

## 🚀 Overview

UnisonAI is a flexible and extensible Python framework for building, coordinating, and scaling multiple AI agents—each powered by the LLM of your choice.

- **Single_Agent:** For solo, focused tasks.
- **Agent (as part of a Clan):** For teamwork, coordination, and distributed problem-solving.
- **Tool System:** Easily augment agents with custom, pluggable tools (web search, time, APIs, your own logic).

Supports Cohere, Mixtral, Groq, Gemini, Grok, OpenAI, Anthropic, and any custom model (just extend `BaseLLM`). UnisonAI is designed for real-world, production-grade multi-agent AI applications.

---

## 🎯 Why UnisonAI?

<div align="center">

<table>
  <tr>
    <td>🔗 <b>Multi-LLM Support</b><br>Mix and match LLM providers with ease.</td>
    <td>🧩 <b>Modular & Extensible</b><br>Add your own tools, LLMs, and logic.</td>
    <td>🤖 <b>Single or Multi-Agent</b><br>Solo agents or collaborative Clans—your call.</td>
  </tr>
  <tr>
    <td>🛡️ <b>Robust Error Handling</b><br>Built-in JSON/YAML repair & retries.</td>
    <td>📚 <b>Clear Docs & Examples</b><br>Well-documented APIs and quick starts.</td>
    <td>⚡ <b>Production-Ready</b><br>Designed for real-world automation & chatbots.</td>
  </tr>
</table>
</div>

---

## 🛠️ Installation

> **Requires Python >=3.10, <3.13**

```bash
pip install unisonai
# or
pip3 install unisonai
```

---

## 🧩 Core Components

<div align="center">

<table>
  <tr>
    <th align="center">Component</th>
    <th align="center">Purpose</th>
    <th align="center">Highlights</th>
  </tr>
  <tr>
    <td><b>Single_Agent</b></td>
    <td>Standalone agent for independent tasks</td>
    <td>
      <ul>
        <li>Own log/history</li>
        <li>Plug in any LLM/tools</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Agent</b></td>
    <td>Works with others in a Clan (team)</td>
    <td>
      <ul>
        <li>Inter-agent messaging</li>
        <li>Tools & role-based prompts</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Clan</b></td>
    <td>Manages a team of Agents (including a leader/manager)</td>
    <td>
      <ul>
        <li>Coordinated planning</li>
        <li>Shared instructions/goals</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Tool System</b></td>
    <td>Extend agent capabilities with custom logic</td>
    <td>
      <ul>
        <li>Reusable, pluggable tools</li>
        <li>Strongly-typed parameters</li>
      </ul>
    </td>
  </tr>
</table>
</div>

---

## 📊 Parameter Reference Tables

### Single_Agent

| Parameter        | Type              | Description                  | Default     |
|------------------|-------------------|------------------------------|-------------|
| `llm`            | BaseLLM/any LLM   | LLM for the agent            | **Required**|
| `identity`       | String            | Agent's unique name          | **Required**|
| `description`    | String            | Agent’s purpose              | **Required**|
| `verbose`        | Boolean           | Verbose/debug mode           | True        |
| `tools`          | List              | Usable tools                 | []          |
| `output_file`    | String            | Output file path             | None        |
| `history_folder` | String            | Directory for logs/history   | "history"   |

### Agent

| Parameter        | Type              | Description                  | Default     |
|------------------|-------------------|------------------------------|-------------|
| `llm`            | Gemini/any LLM    | LLM for the agent            | **Required**|
| `identity`       | String            | Agent's unique name          | **Required**|
| `description`    | String            | Responsibilities overview    | **Required**|
| `task`           | String            | Agent’s core goal/task       | **Required**|
| `verbose`        | Boolean           | Verbose/debug mode           | True        |
| `tools`          | List              | Usable tools                 | []          |

### Clan

| Parameter           | Type      | Description                          | Default     |
|---------------------|-----------|--------------------------------------|-------------|
| `clan_name`         | String    | Name of the clan                     | **Required**|
| `manager`           | Agent     | Clan manager/leader                  | **Required**|
| `members`           | List      | List of Agent instances              | **Required**|
| `shared_instruction`| String    | Instructions for all agents          | **Required**|
| `goal`              | String    | Unified clan objective               | **Required**|
| `history_folder`    | String    | Log/history folder                   | "history"   |
| `output_file`       | String    | Final output file                    | None        |

### BaseTool & Field

**BaseTool**

| Attribute/Method | Description                         |
|------------------|-------------------------------------|
| `name`           | Tool name                           |
| `description`    | Tool function summary               |
| `params`         | List of Field objects (inputs)      |
| `_run(**kwargs)` | Tool logic implementation           |

**Field**

| Attribute         | Description                         | Default   |
|-------------------|-------------------------------------|-----------|
| `name`            | Parameter name                      | **Required**|
| `description`     | Parameter purpose                   | **Required**|
| `default_value`   | Default value                       | None      |
| `required`        | Is parameter mandatory?             | True      |

---

## 💡 Usage Examples

### 🚦 Standalone Agent

This is the code from [`main.py`](https://github.com/UnisonAI/UnisonAI/blob/main/main.py) FILE.

```python
from unisonai import Single_Agent
from unisonai.llms import Gemini
from unisonai.tools.websearch import WebSearchTool

web_agent = Single_Agent(
    llm=Gemini(model="gemini-2.0-flash"),
    identity="Web Explorer",
    description="Web Searcher for multiple queries",
    tools=[WebSearchTool],
    history_folder="history",
    output_file="output.txt"
)

web_agent.unleash(task="Find out what is the age of Trump")
```

---

### 🤖 Clan-Based Agents

This is a refernce from [`main2.py`](https://github.com/UnisonAI/UnisonAI/blob/main/main2.py) FILE, check the file for the full complex example.

```python
from unisonai import Agent, Clan
from unisonai.llms import Gemini
from unisonai.tools.websearch import WebSearchTool

time_agent = Agent(
    llm=Gemini(model="gemini-2.0-flash"),
    identity="Time Keeper",
    description="Handles scheduling",
    task="Track time-related info for the trip",
    tools=[TimeTool]
)

web_agent = Agent(
    llm=Gemini(model="gemini-2.0-flash"),
    identity="Web Explorer",
    description="Searches for travel info",
    task="Gather travel info, cultural activities, and costs",
    tools=[WebSearchTool]
)

clan = Clan(
    clan_name="Ultimate Trip Expert Clan",
    manager=planner_agent,  # Your clan leader agent
    members=[time_agent, web_agent /*, ...other agents*/],
    shared_instruction="Collaborate to plan a budget-friendly 7-day trip in India.",
    goal="Plan a 7-day itinerary across multiple cities with a budget of 10,000 INR",
    history_folder="trip_history",
    output_file="trip_plan.txt"
)

clan.unleash()
```

---

## ❓ FAQ

<details>
  <summary><b>What is UnisonAI?</b></summary>
  <p>A Python framework for orchestrating multiple AI agents—each powered by your choice of LLMs, working solo or in teams.</p>
</details>

<details>
  <summary><b>Why use a Clan?</b></summary>
  <p>For complex, multi-step, or specialized tasks: divide and conquer with specialized agents, coordinated by a manager.</p>
</details>

<details>
  <summary><b>Can I add my own LLM?</b></summary>
  <p>Yes! Just extend the <code>BaseLLM</code> class and plug in your model.</p>
</details>

<details>
  <summary><b>What are tools?</b></summary>
  <p>Reusable logic/components, built on <code>BaseTool</code>, that agents can call for specialized tasks (e.g., web search, APIs).</p>
</details>

<details>
  <summary><b>How is agent history logged?</b></summary>
  <p>Each agent maintains its own logs/history in the specified directory (default: <code>history/</code>).</p>
</details>

<details>
  <summary><b>What can I build with UnisonAI?</b></summary>
  <p>Chatbots, collaborative planners, research assistants, workflow automation, and more!</p>
</details>

---

## 🤝 Contributing and License

<div align="center">

<b>Founder:</b> <a href="https://github.com/E5Anant">@E5Anant</a> <br/>
PRs and issues welcome! The project is under the MIT License.

<a href="https://github.com/UnisonAI/UnisonAI/issues">Open issues</a> •
<a href="https://github.com/UnisonAI/UnisonAI/pulls">Submit PRs</a> •
<a href="https://github.com/UnisonAI/UnisonAI">Suggest improvements</a>

<br/><br/>

<a href="https://github.com/UnisonAI/UnisonAI/blob/main/LICENSE">
  <img src="https://img.shields.io/badge/License-MIT-green.svg?style=flat-square" alt="License: MIT"/>
</a>

</div>

---

<div align="center">
  <b>UnisonAI: Orchestrate the Future of Multi-Agent AI.</b>
</div>
