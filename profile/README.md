# PACT — Prompt-Attack Countermeasure Toolkit

PACT sits between your application and its LLM. When a request comes in, it runs through a chain of defenses: a regex pre-filter, a vector similarity check, a DistilBERT classifier, and a multi-model consensus vote. Each layer is faster and cheaper than the next, so most attacks are blocked early. Responses are scanned for PII before they reach the user, and any tool calls the LLM wants to make are gated by capability tokens.

## Services

| Repo | Language | Role |
|---|---|---|
| [pact-gateway](../pact-gateway) | Go | Reverse proxy, routes requests through the defense chain |
| [pact-filter](../pact-filter) | Go | Regex and vector similarity pre-filter |
| [pact-redactor](../pact-redactor) | Go | PII detection and redaction on responses |
| [pact-policy](../pact-policy) | Go | MCP capability token issuance and tool-call gating |
| [pact-audit](../pact-audit) | Go | Async audit logging via message queue |
| [pact-classifier](../pact-classifier) | Python | DistilBERT single-model inference |
| [pact-consensus](../pact-consensus) | Python | Multi-model consensus vote |
| [pact-dashboard](../pact-dashboard) | TypeScript | Monitoring dashboard |
| [pact-benchmark](../pact-benchmark) | Python | Evaluation against attack corpora |

## Getting started

```bash
git clone git@github.com:PACT-Toolkit/pact.git
cd pact
docker compose up
```
