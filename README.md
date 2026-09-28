# 🚀 Multi-Tool AI Assistant

An intelligent **multi-tool AI assistant** built with **LangChain** that automatically selects the appropriate tool based on the user's query.

The assistant integrates **Web Search, Weather, and PDF-based RAG** into a single conversational AI application, with **chat history management and LangSmith observability**.

---

## 🎯 Project Objective

Build an AI assistant capable of understanding user queries and dynamically selecting the right tool to generate relevant responses.

### The assistant can:

* 🔎 Search the web for current and recent information
* 🌤️ Retrieve live weather information
* 📄 Answer questions from uploaded PDF documents using RAG
* 💬 Maintain conversational context
* 📊 Trace and monitor agent/tool execution using LangSmith

---

## 🏗️ Architecture

```text
                         User Query
                             │
                             ▼
                    ┌─────────────────┐
                    │    AI Agent     │
                    │   LangChain     │
                    └────────┬────────┘
                             │
                    Tool Selection
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                  │
          ▼                  ▼                  ▼
   ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
   │ Web Search  │    │   Weather   │    │   PDF RAG   │
   │  SerpAPI    │    │ OpenWeather │    │    FAISS    │
   └─────────────┘    └─────────────┘    └─────────────┘
          │                  │                  │
          └──────────────────┼──────────────────┘
                             ▼
                    ┌─────────────────┐
                    │    Response     │
                    └─────────────────┘

                  LangSmith Observability
```

---

## 🛠️ Technology Stack

| Technology            | Purpose                      |
| --------------------- | ---------------------------- |
| Python                | Core programming             |
| LangChain             | Agent and tool orchestration |
| OpenRouter            | LLM API integration          |
| SerpAPI               | Web search                   |
| OpenWeather API       | Current weather data         |
| FAISS                 | Vector similarity search     |
| Sentence Transformers | Text embeddings              |
| LangSmith             | Tracing and observability    |
| Google Colab          | Development environment      |

---

## 🔧 Key Features

### 1. 🔎 Web Search

The assistant uses **SerpAPI** when the query requires current, recent, or time-sensitive information.

Example:

```text
What are the latest developments in Generative AI?
```

---

### 2. 🌤️ Weather Tool

The assistant retrieves current weather information using the **OpenWeather API**.

The tool can provide:

* Temperature
* Humidity
* Wind information
* Weather conditions

Example:

```text
What is the current weather in Hyderabad?
```

---

### 3. 📄 PDF RAG

The project implements **Retrieval-Augmented Generation (RAG)** for answering questions from uploaded PDF documents.

#### RAG Pipeline

```text
PDF Document
     ↓
Text Extraction
     ↓
Document Chunking
     ↓
Sentence Transformer Embeddings
     ↓
FAISS Vector Store
     ↓
Similarity Search
     ↓
Relevant Context
     ↓
LLM Response
```

The implementation uses:

* `sentence-transformers/all-MiniLM-L6-v2`
* FAISS
* Chunk size: 400
* Chunk overlap: 100

---

### 4. 💬 Chat History

The assistant maintains conversational context using chat history.

To control memory size, only the **latest 10 message objects** are retained.

This helps demonstrate practical conversation-state management while preventing unlimited history growth.

---

### 5. 📊 LangSmith Observability

**LangSmith** is used to trace and monitor:

* Agent execution
* Tool selection
* Tool calls
* Execution flow
* Responses

This provides visibility into how the AI agent processes user requests.

---

## 🧪 Example Queries

### Web Search

```text
What are the latest developments in Generative AI?
```

### Weather

```text
What is the current weather in Hyderabad?
```

### PDF RAG

```text
What are the major achievements mentioned in the uploaded PDF?
```

### Conversational Query

```text
What is the weather in Hyderabad?
```

Follow-up:

```text
What about the humidity?
```

---

## 📂 Project Structure

```text
Multi-Tool-AI-Assistant/
│
├── Multi_Tool_AI_Assistant.ipynb
├── README.md
├── .gitignore
└── .env.example
```

> `.env` contains API credentials and is intentionally excluded from GitHub.

---

## 🔐 Environment Variables

Create a `.env` file locally with the following variables:

```env
OPENROUTER_API_KEY=your_api_key
SERPAPI_API_KEY=your_api_key
OPENWEATHER_API_KEY=your_api_key
LANGSMITH_API_KEY=your_api_key

LANGSMITH_TRACING=true
LANGSMITH_PROJECT=Multi-Tool-AI-Assistant
```

**Never commit API keys or other secrets to GitHub.**

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/multi-tool-ai-assistant.git
```

### 2. Navigate to the project

```bash
cd multi-tool-ai-assistant
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

> If using Google Colab, install the required packages directly in the notebook.

### 4. Configure API keys

Create a `.env` file and add the required API credentials.

### 5. Run the notebook

Open:

```text
Multi_Tool_AI_Assistant.ipynb
```

in Google Colab or Jupyter Notebook.

---

## 📈 Project Highlights

* Built a **single AI agent capable of selecting between multiple tools**
* Implemented **RAG using FAISS and sentence-transformer embeddings**
* Integrated external APIs for **real-time information retrieval**
* Implemented **conversation history management**
* Added **LangSmith tracing for observability**
* Designed the workflow around practical **LLM tool-calling and orchestration**

---

## 🔮 Future Enhancements

* Add additional tools such as SQL/database querying
* Implement long-term conversational memory
* Add document upload through a web interface
* Deploy as a Streamlit application
* Add authentication and user-level sessions
* Implement evaluation metrics for RAG responses
* Add guardrails and structured output validation
* Containerize and deploy using Docker
* Add automated testing and CI/CD

---

## 👨‍💻 Author

**Shiva Prasad Reddy Bitla**

Generative AI | AI Solutions | Technical Consulting

---

## ⭐ Project Purpose

This project demonstrates practical implementation of:

**LLMs + Agents + Tool Calling + RAG + APIs + Memory + Observability**

and serves as a foundation for building production-oriented Generative AI applications.
