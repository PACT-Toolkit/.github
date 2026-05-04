# PACT — Prompt-Attack Countermeasure Toolkit

PACT sits between your application and its LLM. When a request comes in, it runs through a chain of defenses: a regex pre-filter, a secrets scanner, a vector similarity check, a DistilBERT classifier, and a multi-model consensus vote. Each layer is faster and cheaper than the next, so most attacks are blocked early. Responses are scanned for PII before they reach the user, and any tool calls the LLM wants to make are gated by capability tokens.

## What it protects against

- **Prompt injection** — attackers hiding malicious instructions inside user input
- **Secret leakage** — credentials and API keys accidentally included in prompts
- **PII leaks** — sensitive data appearing in LLM responses
- **Unauthorized tool calls** — the LLM being manipulated into taking actions it should not

## Getting started

Contact the maintainers for access to the service repositories.
