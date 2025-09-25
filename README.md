# Podcast Script Brewer 🎙️

A stateful AI agent that collaboratively writes podcast scripts, incorporating human feedback through an iterative loop built with LangGraph's powerful conditional logic.

## 📜 Overview

This project showcases how to build a sophisticated, stateful AI agent using Python and **LangGraph**. Unlike simple "fire-and-forget" generators, the Podcast Script Brewer engages in a collaborative writing process. It researches a topic, drafts a script, and then pauses to wait for human feedback. Based on your notes, it will revise the script in a continuous loop until you approve the final version.

This repository contains two key examples:

1.  **`01_foundational_script_agent.ipynb`**: A notebook detailing the creation of a simple, linear agent that researches and writes a single draft. This is the perfect starting point for understanding the basics of LangGraph.
2.  **`02_human_in_the_loop_agent.ipynb`**: The advanced version. This notebook builds upon the first by adding a feedback loop, conditional logic, and interrupts, turning the simple generator into a truly interactive AI partner.

---

## ✨ Features

-   **Autonomous Research**: Kicks off the process by using the Tavily Search API to research any given topic.
-   **Structured Content Generation**: Synthesizes research into key points before writing the final script.
-   **Iterative Feedback Loop**: The core feature! The agent presents its draft, listens to your feedback, and intelligently revises its work.
-   **Conditional State Transitions**: Built with a conditional graph that decides whether to finish or revise based on user input.
-   **Human-in-the-Loop Architecture**: Uses LangGraph `interrupts` to explicitly pause the agent and wait for human input, a key pattern for building interactive AI systems.

---

## 🛠️ Tech Stack

-   **Python 3.9+**
-   **LangGraph & LangChain**: For building the stateful agent graph.
-   **GEMINI API**: For the core language model (GPT-4o-mini).
-   **Tavily Search API**: For real-time web research.
-   **Jupyter Notebooks**: For interactive development and demonstration.

---

## Getting Started

Follow these steps to get the Podcast Script Brewer running on your local machine.

### 1. Clone the Repository

```bash
git clone https://github.com/jascodebrewer/langgraph-podcast-agent.git
cd langgraph-podcast-agent
```
### 2. Set Up a Virtual Environment
```bash
# For Mac/Linux
python3 -m venv venv
source venv/bin/activate

# For Windows
python -m venv venv
venv\Scripts\activate
```

### 3. Install Dependencies
Install all the required Python libraries from the requirements.txt file.
```bash
pip install -r requirements.txt
```

### 4. Configure API Keys
The agent requires API keys from GEMINI/OPENAI and Tavily. The easiest way to manage these is by creating a .env file in the root of the project directory.

```bash
OPENAI_API_KEY="sk-..."
TAVILY_API_KEY="tvly-..."
```
The Python scripts are configured to automatically load these keys.

## How to Run
Once your setup is complete, you can explore the agent's functionality by running the Jupyter Notebooks:

1. Start Jupyter Lab:
```bash
jupyter lab
```
2. Open 01_foundational_script_agent.ipynb to see the basic, linear agent in action.
3. Open 02_human_in_the_loop_agent.ipynb to interact with the advanced agent. Run the cells sequentially and provide your own feedback when prompted!

##  Future Improvements
This project serves as a strong foundation. Here are a few ideas for extending it:
1. **Web Interface**: Build a simple web UI with Streamlit or Flask to make the interaction more user-friendly.
2. **Multi-Agent System**: Add a "Critic" agent that automatically provides feedback on the script before it's shown to the human.
3. **Persistent Memory**: Integrate LangSmith or a database to give the agent memory of past conversations.
