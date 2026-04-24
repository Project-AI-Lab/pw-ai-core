# Project's AI Core

`ai-core` provides the **foundational infrastructure** for all AI systems in the lab.

It is intentionally minimal, stable, and dependency-free from application logic.

---

## 🧠 Purpose

Provide shared building blocks such as:
- model abstraction
- API clients
- configuration management
- logging & tracing
- error handling

---

## 🧱 Design Principle

> **Core should be stable and generic.**

- No business logic
- No use-case specific code
- No workflow logic

---

## 📦 What Belongs Here

- LLM client wrappers (Claude, etc.)
- request/response normalization
- retry logic
- rate limiting
- config loaders
- logging utilities

---

## 🚫 What Does NOT Belong Here

- prompts
- RAG pipelines
- workflows
- agents
- evaluation logic
- application code

👉 These belong in `pw-ai-capabilities` or `pw-ai-apps`

---

## 🔁 Dependency Rules

- `pw-ai-core` depends on nothing
- Everything else depends on `pw-ai-core`

---

## 🧭 Example Usage

```python
from pw_ai_core.llm import ClaudeClient

client = ClaudeClient()
response = client.generate(prompt)