# System Architecture

## Overview

ARIA is designed as a modular, production-oriented system composed of three layers:

* **Client Layer** — user interface and interaction
* **API Layer** — orchestration, validation, and routing
* **Intelligence Layer** — language models and semantic retrieval

Each layer is independently scalable and communicates via standard interfaces.

---

## High-Level Architecture

```
Client (React)
    ↓
API Layer (FastAPI)
    ↓
Orchestration Layer
    ↓
LLM + Embeddings + Vector Search
```

---

## Client Layer

The frontend is responsible for interaction and real-time feedback.

**Key responsibilities:**

* Chat interface and conversational flow
* Product discovery and rendering
* Outfit visualisation
* Streaming responses for improved UX

The client communicates with the backend using REST and streaming where appropriate.

---

## API Layer

The API layer acts as the control plane of the system.

**Responsibilities:**

* Request validation
* Routing to appropriate capabilities
* Response formatting
* Error handling

All incoming and outgoing data is strongly typed to ensure consistency.

---

## Orchestration Layer

This is the core intelligence coordinator.

It manages:

* Prompt selection based on task
* Context injection (user input, session state, product data)
* Model invocation
* Post-processing and validation

This layer ensures that each feature behaves predictably despite relying on probabilistic models.

---

## Intelligence Layer

ARIA combines language models with vector search to balance reasoning quality and efficiency.

### Language Model

Used for:

* Intent understanding
* Response generation
* Ranking decisions
* Structured output generation

---

### Semantic Retrieval

Used for:

* Product discovery
* Candidate generation

The system retrieves a small, relevant subset of products before applying deeper reasoning.

---

## Core Request Flows

### Chat Stylist

1. User submits a message
2. Request is validated and enriched with session context
3. Model generates structured response
4. If needed, product retrieval and ranking are triggered
5. Final response returned and rendered

---

### Semantic Search

1. Query is converted into a semantic representation
2. Candidate products are retrieved
3. Results are refined based on contextual relevance
4. Top matches returned to the client

---

### Outfit Builder

1. User selects an anchor item and context (e.g. occasion)
2. Candidate items are retrieved
3. Model composes a complete outfit
4. Output is validated and returned

---

### Review Intelligence

1. Raw reviews are provided as input
2. Model extracts key signals
3. Structured summary is generated
4. Output is validated before delivery

---

## Session Management

ARIA maintains short-term conversational context within a session.

* Early turns use full conversation history
* Longer sessions are compressed into structured summaries
* Context remains bounded to ensure performance and cost control

---

## Data Validation

All model outputs are validated before reaching the client.

This ensures:

* Consistent structure
* Safe and predictable UI rendering
* Early detection of malformed responses

---

## Deployment Model

ARIA is deployed as two independent services:

* **Frontend** — statically deployed and globally distributed
* **Backend** — API service with access to model and retrieval layers

This separation allows:

* Independent scaling
* Faster iteration cycles
* Flexible integration into existing systems

---

## Design Principles

* **Separation of concerns** — UI, logic, and intelligence are decoupled
* **Deterministic interfaces** — all outputs are structured and validated
* **Efficiency first** — retrieval limits model workload
* **Extensibility** — new capabilities can be added without redesign

---

## Summary

ARIA’s architecture is designed to make LLM-driven features reliable, scalable, and production-ready.

It combines:

* deterministic system design
* probabilistic intelligence
* structured interfaces

to deliver a consistent user experience.
