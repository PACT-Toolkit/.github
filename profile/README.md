# PACT — Prompt-Attack Countermeasure Toolkit

PACT sits between your application and its LLM. When a request comes in, it runs through a chain of defenses: a regex pre-filter, a vector similarity check, a DistilBERT classifier, and a multi-model consensus vote. Each layer is faster and cheaper than the next, so most attacks are blocked early. Responses are scanned for PII before they reach the user, and any tool calls the LLM wants to make are gated by capability tokens.

## What it protects against

- **Prompt injection** — attackers hiding malicious instructions inside user input
- **PII leaks** — sensitive data appearing in LLM responses
- **Unauthorized tool calls** — the LLM being manipulated into taking actions it should not

## Bachelor project

Built as a 3-month bachelor project at Aarhus University by two software engineering students. The project explores layered LLM defense in the context of EU AI Act compliance for fintech applications.

## Getting started

Contact the maintainers for access to the service repositories.
