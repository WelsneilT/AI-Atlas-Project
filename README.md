# ATLAS: AI-Powered Multi-Agent System for Personalized Education

**ATLAS (Adaptive Tutoring & Learning Assistant System)** is a sophisticated multi-agent system designed to act as a personal AI tutor for students. It goes beyond simple Q&A by understanding a student's schedule, tasks, and learning style to provide comprehensive, actionable support.

## 🚀 Core Features

-   **Personalized Planning**: Integrates with Google Calendar to analyze a student's real-world schedule and craft detailed, realistic study plans.
-   **Intelligent Research**: Utilizes the Tavily search engine to gather, synthesize, and summarize information on any academic topic, tailored to the student's learning preferences.
-   **Strategic Advice**: Provides high-level advice on study methods, time management, and overcoming academic challenges.
-   **Dynamic & Adaptive**: Uses a Coordinator agent to analyze user requests and dispatch tasks to the most suitable specialized agent, ensuring a relevant and effective response.

## 🏗️ System Architecture

ATLAS is built on a multi-agent graph architecture powered by LangGraph. The workflow is orchestrated by a central Coordinator agent that routes tasks based on the user's needs.

```text
User Request
     │
     ▼
┌───────────────────┐
│ 🧠 Coordinator    │  (Analyzes request and decides the required agents)
└───────────────────┘
     │
     ▼
┌───────────────────┐
│      Router       │
└───────────────────┘
     │
     ├───► 📅 **Planner Agent** (Manages schedule, tasks, creates plans)
     │
     ├───► 🔎 **NoteWriter Agent** (Researches topics, creates summaries)
     │
     └───► 🌱 **Advisor Agent** (Provides strategic study advice)
     │
     ▼
┌───────────────────┐
│ Final Response    │  (Aggregated results from all active agents)
└───────────────────┘
```

### Meet the Agents

-   **🧠 Coordinator Agent**: The "brain" of the operation. It parses the initial user prompt to determine which specialized agents are needed for the task (e.g., `PLANNER`, `NOTEWRITER`).
-   **📅 Planner Agent**: The "time manager". It fetches data from Google Calendar and a local task list to analyze the student's workload and generate a detailed, day-by-day study schedule.
-   **🔎 NoteWriter Agent**: The "research assistant". It uses the Tavily Search API to find relevant information on the web, then formats the findings into clear, structured notes based on the student's preferred learning style (e.g., visual, text-based).
-   **🌱 Advisor Agent**: The "strategic coach". It analyzes the student's overall situation to provide high-level advice on learning techniques, motivation, and how to effectively use the generated plan and notes.

## 🛠️ Tech Stack

-   **Framework**: LangChain & LangGraph
-   **LLM Provider**: Groq (for blazingly fast inference)
-   **Search Tool**: Tavily Search API
-   **Productivity Tool**: Google Calendar API
-   **Core Language**: Python
