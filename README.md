# FastAPI + LLM Intelligent News & Chat Platform

This project extends a FastAPI-based news backend (inspired by a beginner course) by integrating large language model (LLM) capabilities with persistent context memory. It is designed as a hands-on system to demonstrate how to build a production-style AI application with real-time interaction and structured backend architecture.

The platform showcases how a modern **asynchronous Python web framework** can be combined with **LLM-powered dialogue, streaming responses, and retrieval-augmented generation (RAG)** to create an intelligent news assistant. It is especially suitable as a practical reference for **FastAPI beginners and prompt engineering workflows**.

---

## Key Features

### High-Performance Async Backend

* Built with **FastAPI + Async SQLAlchemy**
* Fully asynchronous, non-blocking I/O design
* Optimized for high-concurrency LLM API calls and real-time streaming

### LLM Integration (AI Chat)

* Integrated with LLM APIs (e.g., DashScope / Tongyi Qianwen)
* Uses **Server-Sent Events (SSE)** for low-latency streaming responses
* Provides a smooth, ChatGPT-like typing interaction experience

### Intelligent Session & Context Management

* Persistent user system: registration, login, and multi-session support
* Session-level conversation tracking and switching
* Context memory with:

  * Conversation summarization
  * History compression for long dialogues
  * Token usage optimization

### RAG Pipeline (LangChain-based)

* Built with **LangChain + Chroma vector database**
* Pipeline includes:

  * Document chunking
  * Embedding
  * Vector retrieval
  * Prompt engineering
  * LLM generation
* Retrieves real news data from the database to reduce hallucination
* Ensures responses are **accurate, grounded, and traceable**

### Data Integrity & Security

* Strict schema validation using **Pydantic v2**
* Unified API response format
* Clear separation between ORM models and external API schemas
* Prevents leakage of sensitive data (e.g., password hashes)

### Complete Backend Workflow

* RESTful APIs with:

  * JWT-based authentication
  * News categorization
  * Reading history tracking
  * Article bookmarking

### Frontend Integration

* Built with **Vue 3 + Pinia (SPA)**
* Fully integrated with backend APIs and SSE streaming
* Supports real-time chat and session state synchronization

---

## Tech Stack

### Backend & LLM Engineering

* **Framework**: FastAPI (async-native, OpenAPI support)
* **Database / ORM**: SQLAlchemy (AsyncSession) + SQLite
  *(easily extensible to PostgreSQL/MySQL)*
* **LLM Framework**: LangChain
* **Vector Store**: Chroma
* **Prompt Engineering**: Custom-designed prompts for domain-specific (news-focused) conversational AI

### Frontend

* **Framework**: Vue 3 (Composition API) + Vite
* **State Management**: Pinia
* **HTTP Client**: Axios (with interceptors for auth/token handling)

---

## Project Architecture

```text
backend/
├── config/        # Configuration (DB, environment)
├── crud/          # Async database operations
├── models/        # SQLAlchemy models
├── routers/       # API routes
├── schemas/       # Pydantic validation schemas
├── services/      # Core logic (RAG, chat, summarization)
├── utils/         # Utilities (JWT, error handling)
└── main.py        # App entry point

frontend/
├── src/
│   ├── store/     # State management (chat/session sync)
│   └── views/     # UI pages (chat interface)
└── package.json
```

---

## Summary

This project demonstrates how to design a **production-oriented AI backend system** by combining:

* Asynchronous web architecture (FastAPI)
* Real-time LLM streaming interaction (SSE)
* Context-aware conversation management
* Retrieval-Augmented Generation (RAG)

It serves as a practical template for building **scalable AI applications**, especially in domains requiring **structured knowledge grounding and conversational interfaces**.

