# PACT — Prompt-Attack Countermeasure Toolkit

PACT sits between your application and its LLM. When a request comes in, it runs through a chain of defenses: a regex pre-filter, a secrets scanner, a vector similarity check, a DistilBERT classifier, and a multi-model consensus vote. Each layer is faster and cheaper than the next, so most attacks are blocked early. Responses are scanned for PII before they reach the user, and any tool calls the LLM wants to make are gated by capability tokens.

## OWASP LLM Top 10 coverage

PACT covers 8 of the [OWASP LLM Top 10](https://genai.owasp.org/llm-top-10/) through its runtime service architecture. No mitigations require changes to your model or training pipeline.

| Risk | Coverage | How |
|---|---|---|
| LLM01 Prompt Injection | ✅ | `pact-filter` injection rule set + `pact-classifier` injection label |
| LLM02 Sensitive Information Disclosure | ✅ | `pact-classifier` + `pact-redactor` + `pact-filter` + `pact-policy` |
| LLM03 Supply Chain | — | Training-time concern, out of scope |
| LLM04 Data & Model Poisoning | — | Training-time concern, out of scope |
| LLM05 Improper Output Handling | ✅ | `pact-filter` and `pact-redactor` run bidirectionally on inputs and outputs |
| LLM06 Excessive Agency | ✅ | `pact-policy` defines and enforces agent capability/permission boundaries |
| LLM07 System Prompt Leakage | ✅ | `pact-redactor` strips system prompt patterns from responses |
| LLM08 Vector & Embedding Weaknesses | ✅ | `pact-classifier` labels embedding inputs; `pact-filter` enforces retrieval policies |
| LLM09 Misinformation | — | Requires external grounding infrastructure, out of scope |
| LLM10 Unbounded Consumption | ✅ | `pact-gateway` rate limiting + `pact-benchmark` quota tracking |

## Services

| Service | Role |
|---|---|
| pact-gateway | API gateway — single entry point; enforces rate limits and quotas |
| pact-classifier | Classifies data for sensitivity, category, and prompt injection patterns |
| pact-policy | Policy management, evaluation, and agent scope/permission definitions |
| pact-redactor | Redacts sensitive data and system prompt patterns from inputs and outputs |
| pact-filter | Filters content against policy rules, bidirectionally on inputs and outputs |
| pact-audit | Audit trail and event logging |
| pact-consensus | Consent and approval flows |
| pact-benchmark | Performance benchmarking and consumption quota tracking |

## Getting started

Contact the maintainers for access to the service repositories.
