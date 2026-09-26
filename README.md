# agent-eval-framework
Production-grade LLM agent evaluation pipeline featuring Pydantic schema validation, tool trajectory testing, LLM-as-a-Judge quality checks, and security guardrails.
# LLM Agent Evaluation & Guardrail Pipeline

A production-grade evaluation framework for an agentic banking assistant. This project demonstrates how to build a reliable tool-calling agent using Pydantic schema validation and evaluate it using an **LLM-as-a-Judge** workflow, tool trajectory testing, and safety guardrails integrated into Pytest.

---

## Architecture Overview


User Prompt
    │
    ▼
[ Agent Core (Groq / Qwen / Llama-3) ]
    │
    ├── System Prompt & Guardrails (Redacts Confidential Tokens)
    ├── Tool Calling (mock_get_account_balance)
    └── Pydantic Schema Validation (AccountBalanceRequest)
    │
    ▼
[ Evaluation Suite (Pytest) ]
    ├── Schema Validation Tests (Input Contracts)
    ├── Trajectory Tests (Tool Selection & Parameter Extraction)
    ├── LLM-as-a-Judge Quality Tests (Single-Answer Grading)
    └── Security & Jailbreak Guardrail Tests
    │
    ▼
[ CI/CD Pipeline (GitHub Actions) ]
