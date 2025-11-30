# Autonomous Agentic RAG Research Assistant 🧠🛠️

An advanced, production-ready **Agentic RAG** system built on **[LlamaIndex](https://developers.llamaindex.ai/python/framework/)** that enables LLMs to perform autonomous, multi-source research by dynamically routing queries and utilizing external web tools.

## 📌 Project Overview
This project upgrades standard RAG by introducing a decision-making layer, allowing the agent to analyze a complex query and intelligently choose the optimal retrieval strategy (local knowledge base, web search, or academic repository). This system is designed for high-accuracy, grounded research over domain-specific documents.

**Key Objectives:**
- Implement a **Router Query Engine** for dynamic query distribution.
- Integrate **multi-tool capabilities** for real-time external knowledge augmentation.
- Deploy an end-to-end observability framework for agent debugging and evaluation.

## 🏗️ Architecture & Features

### 1. Dynamic Routing & Indexing
-   **Router Query Engine:** Utilizes the `LLMSingleSelector` to decide, at runtime, whether a query requires specific context (Vector Index) or a high-level overview (Summary Index).
-   **Dual Indexing:** Structures the private knowledge base into **Vector Store Index** (for semantic retrieval) and **Summary Index** (for summarization), optimizing token usage and answer relevance.

### 2. Multi-Tool Integration
The agent is augmented with external capabilities to perform comprehensive research:
-   **Web Search:** Integrated with **Brave Search API** for up-to-the-minute current events and general web knowledge.
-   **Academic Research:** Integrated with the **ArXiv API** to cross-reference private data with cutting-edge academic papers and studies.

### 3. Observability & Evaluation
-   **Full-Stack Tracing:** Integrated **[Arize AI Phoenix](https://github.com/Arize-ai/phoenix)** for end-to-end LLM observability, enabling detailed trace visualization of agent reasoning chains and tool execution paths.

## 🛠️ Tech Stack
-   **Framework:** LlamaIndex, OpenAI API
-   **Observability:** Arize AI Phoenix
-   **Tools/Connectors:** Brave Search API, ArXiv API
-   **Core Concepts:** Agentic RAG, Router Query Engines, Semantic Search, Multi-Tool Orchestration

## ⚙️ Installation & Setup
1.  **Clone the Repository:**
    ```bash
    git clone [Your Repository URL]
    cd Autonomous Agentic RAG Research Assistant 
    ```
2.  **Install Dependencies:**
    ```bash
    pip install llama-index llama-index-integrations-arize-phoenix brave-search arxiv
    ```
3.  **Set Environment Variables:**
    Set API keys for OpenAI (LLM), Brave Search, and ArXiv (if needed) in your environment or `.env` file.

## 🚀 Usage Example
The agent processes a complex query requiring synthesis of internal and external data:

1.  **Input:** User asks a question comparing the internal document's findings with recent academic papers.
2.  **Router Action:** Agent first queries the **Vector Index** for relevant passages, then calls the **ArXiv Tool** for recent citations.
3.  **Synthesis:** LLM synthesizes the retrieved local and external context to produce a single, grounded response.
4.  **Debugging:** All steps are logged and visible in the **Phoenix Tracing Dashboard** for quality assurance.
