# template-agent-base 🤖

## 1. Context & Architectural Bounds
The `template-agent-base` repository serves as the official standardized starter skeleton for all new autonomous agents onboarded onto the enterprise platform. Following **12-Factor App Principles #1 and #2**, it keeps the local codebase lean and modular by inheriting enterprise security filters, custom instrumentation hooks, and log aggregators from the shared `enterprise-agent-core` dependency.

## 2. Directory Semantics & Governance
* `/app/tools`: Houses the domain execution definitions and third-party API interface logic this agent wields to affect its tasks.
* `/app/prompts`: Stores versioned system identity strings, few-shot prompt training models, and persona context parameters.
* `/app/middleware`: Implements agent-specific data validation routines and validation checks.
* `/tests`: Holds specialized local mock validations verifying that agent tool executions return safe payloads.

## 3. SDLC Compliance Checkpoints
* **Instantiating a New Agent:** Developers must use the `platform-bootstrap` automation loop to copy this template into a new repository (e.g., `fin-prod-agent-billing`), assign the appropriate custom metadata fields, and immediately focus on tools and prompt construction.
* **Security & Auditing:** Every tool file developed inside `/app/tools` must be wrapped with the standard corporate tracking decorator (`@agent_tool`) inherited from your shared core libraries to ensure runtime compliance.
