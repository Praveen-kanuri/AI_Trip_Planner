# AI_Trip_Planner
### Agentic Multi-Step Travel Planning System using LangGraph

AI_Trip_Planner is an agentic travel orchestration engine that performs multi-step reasoning, tool execution, validation, and dynamic re-planning to generate intelligent travel itineraries.

This system goes beyond simple LLM itinerary generation. It uses a structured state machine (LangGraph) to coordinate planning steps, invoke tools, validate constraints, and refine outputs before presenting the final travel plan.

---

## 🧠 System Capabilities

- Multi-step agentic planning
- Tool invocation (weather, currency, expense, place search, arithmetic)
- Constraint validation (budget, timeline, preferences)
- Dynamic re-planning when constraints fail
- Structured reasoning workflow using LangGraph
- Streamlit-based interactive UI
- Modular tool abstraction layer
- Logging & exception handling
- Config-driven architecture

---

## 🏗 System Architecture

AI_Trip_Planner follows a layered, modular architecture:

### 1️⃣ Presentation Layer
- Streamlit-based interactive UI
- Captures user travel intent and constraints

### 2️⃣ Agent Orchestration Layer
- Implemented using LangGraph
- Defines deterministic state transitions
- Handles planning → tool routing → validation → re-planning

### 3️⃣ Tool Layer
- Weather Information
- Currency Conversion
- Expense Calculator
- Place Search
- Arithmetic Operations

Each tool is modularized and decoupled from the agent logic.

### 4️⃣ Utility & Service Layer
- Model Loader (LLM abstraction)
- Config Loader (environment-driven configuration)
- Structured Logging
- Custom Exceptions
- Document Persistence
- External API Wrappers

This layered separation ensures extensibility and maintainability.
---

## 📁 Project Structure
AI_Trip_Planner/

│

├── agent/ # LangGraph agent logic

├── tools/ # Tool implementations

├── config/ # Configuration management

├── logger/ # Structured logging

├── exception/ # Custom exceptions

├── prompt_library/ # Prompt templates

├── utils/ # Utility functions

├── notebook/ # Experimental notebooks

│

├── main.py # Core execution entry point

├── streamlit_app.py # Interactive UI

├── pyproject.toml # Project metadata

├── requirements.txt

└── setup.py

---

## 🔧 Tools Integrated

The agent dynamically selects and invokes:

- Weather Information Tool
- Currency Conversion Tool
- Expense Calculator
- Place Search Tool
- Arithmetic Operations Tool

Each tool follows a modular interface, allowing extension without modifying the core orchestration logic.

---

## ⚙️ Tech Stack

- Python
- LangChain
- LangGraph
- Streamlit
- OpenAI / LLM backend abstraction
- Modular tool architecture
- Structured logging
- Environment-based configuration

---

## 🚀 How It Works (Execution Flow)

1. User submits travel intent (destination, budget, preferences).
2. Planner node generates high-level itinerary structure.
3. Tool-routing node determines required external data.
4. Tools execute asynchronously and return structured outputs.
5. Validation node checks budget and constraints.
6. If validation fails → system re-enters planning loop.
7. Final validated itinerary is presented.

This creates a closed-loop reasoning system rather than a single-pass LLM response.

---

## 🖥 Running the Application

### 1️⃣ Install dependencies
uv pip install -r requirements.txt

### 2️⃣ Configure environment variables

Create a `.env` file with required API keys.

### 3️⃣ Run Streamlit UI
uv streamlit run streamlit_app.py


---

## 🔬 Engineering Design Principles

- Separation of concerns (Agent vs Tool vs Utility)
- Config-driven architecture
- Modular tool registration
- Deterministic state machine orchestration
- Re-planning loop for constraint failures
- Extensible service layer
- Clean project packaging via pyproject.toml

---

## 🔬 Future Improvements

- Multi-agent specialization (budget agent, logistics agent, experience agent)
- RAG integration for destination knowledge
- Persistent user memory
- Cloud deployment (Docker + Kubernetes)
- Latency optimization via async tool calls
- Evaluation metrics for itinerary quality

---

## 📌 Why This Project Matters

AI_Trip_Planner demonstrates how agentic systems can:

- Move beyond single-shot LLM prompts
- Coordinate multiple tools
- Validate outputs
- Perform structured re-planning
- Operate as deterministic reasoning workflows

This project reflects production-oriented design principles applied to generative AI systems.
