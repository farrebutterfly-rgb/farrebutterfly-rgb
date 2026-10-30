### Farre

Stockholm. I build AI agents, retrieval systems and the websites around them, and I run them in production on my own hardware. Founder of [HolgerAI](https://holgerai.com).

---

#### HolgerAI · retrofit autonomy for forklifts

HolgerAI is a Swedish deep tech company. It is building a kit, with its own hardware, designed to make the forklifts a warehouse already owns drive themselves. The software can ask for full throttle, but permission to move runs through a hardware gate that no software can open. Swedish patent application SE 2530598-8 (2025) and PCT application (2026). I designed and built the site.

[![holgerai.com](bilder/holgerai.jpg)](https://holgerai.com)

#### hub-minne · local RAG memory for an agent platform

Retrieval layer for Holger Hub, the platform where my agents (Claude Code, Codex, OpenClaw, Hermes) run around the clock. TypeScript, Mastra, Express and PostgreSQL with pgvector. Hybrid search (vectors plus Postgres full text, fused with Reciprocal Rank Fusion), source weighting, and a Mastra agent answering with citations from a local Qwen model. Nothing leaves the machine.

Measured on a question set with known answers, the share of questions with the right fact in the top 5 went from 45 % with plain vector search to 77 %.

Code: [github.com/farrebutterfly-rgb/hub-minne](https://github.com/farrebutterfly-rgb/hub-minne)

#### Portfolio · eight runnable AI engineering projects

Each repo runs a full demo with no API key, ships its own tests and run logs, and says plainly what it does not prove yet.

| Repo | What it shows |
| --- | --- |
| [agent-toolkit](https://github.com/farrebutterfly-rgb/agent-toolkit) | Tool-calling agent: schema-validated tools, HTTP integration, timeouts, step limit, grounded final answer |
| [grounded-context](https://github.com/farrebutterfly-rgb/grounded-context) | Retrieval with citations checked against source text; three context strategies compared under a token budget |
| [remember-me](https://github.com/farrebutterfly-rgb/remember-me) | Persistent, user-owned memory with correction, deletion and backend-enforced access |
| [review-workflow](https://github.com/farrebutterfly-rgb/review-workflow) | Planner/worker extraction, Python validator and human review, benchmarked against a single agent |
| [agent-evals](https://github.com/farrebutterfly-rgb/agent-evals) | 50 labelled cases, held-out split, regression check that catches degraded systems |
| [sandbox-runner](https://github.com/farrebutterfly-rgb/sandbox-runner) | Sandbox for agent-written Python; 13 isolation controls verified with bubblewrap and unshare |
| [durable-jobs](https://github.com/farrebutterfly-rgb/durable-jobs) | Checkpointed jobs that survive SIGKILL, idempotent requests, bounded retries |
| [agent-api-sdk](https://github.com/farrebutterfly-rgb/agent-api-sdk) | React and TypeScript product with documented API, typed SDK, Python step, auth and rate limits |

#### Products on top of the platform

- **[Relta](https://relta.app)** · AI accounting bureau for Swedish companies. Built so that agents do the bookkeeping and an authorized accountant reviews and signs off. Deployed on Vercel and Neon with Stripe, BankID and bank connection. A PKI certificate from Expisoft ties the organisation e-ID to the company registration number.
- **[Lexra](https://lexra.se)** · AI-driven law firm. Built so that agents draft and review and a licensed lawyer signs. Contract review scored 87 % recall and 100 % precision on our own test set.
- **[Wattvik](https://wattvik.com)** · co-founder. Monitoring of electronic component shortages and sourcing for B2B buyers.

#### Also

- **Regla**, a concept for automating paperwork in Swedish civil construction: design system in Figma (variables, 14 text styles, mobile and web screens) and a pitch deck with CAD-style drawings.

---

**Stack** · TypeScript, Node.js, Express, Python, React, Next.js, PostgreSQL, pgvector, Mastra, Claude API, OpenAI, local models via LM Studio, Lovable, Vercel, Figma

**Languages** · Swedish and English (native), Tigrinya and Arabic (B2)

farre@holgerai.com
