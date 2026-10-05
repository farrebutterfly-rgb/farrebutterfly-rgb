### Farre

Stockholm. I build AI agents, retrieval systems and the websites around them, and I run them in production on my own hardware. Founder of [HolgerAI](https://holgerai.com).

---

#### HolgerAI · retrofit autonomy for forklifts

HolgerAI is a Swedish deep tech company. It builds a kit, with its own hardware, that makes the forklifts a warehouse already owns drive themselves. The software can ask for full throttle, but permission to move runs through a hardware gate that no software can open. Swedish patent application SE 2530598-8 (2025) and PCT application (2026). I designed and built the site.

[![holgerai.com](bilder/holgerai.jpg)](https://holgerai.com)

#### hub-minne · local RAG memory for an agent platform

Retrieval layer for Holger Hub, the platform where my agents (Claude Code, Codex, OpenClaw, Hermes) run around the clock. TypeScript, Mastra, Express and PostgreSQL with pgvector. Hybrid search (vectors plus Postgres full text, fused with Reciprocal Rank Fusion), source weighting, and a Mastra agent answering with citations from a local Qwen model. Nothing leaves the machine.

Measured on a question set with known answers, the share of questions with the right fact in the top 5 went from 45 % with plain vector search to 77 %.

→ [github.com/farrebutterfly-rgb/hub-minne](https://github.com/farrebutterfly-rgb/hub-minne)

#### Also

- **Regla**, a concept for automating paperwork in Swedish civil construction: design system in Figma (variables, 14 text styles, mobile and web screens) and a pitch deck with CAD-style drawings.

---

**Stack** · TypeScript, Node.js, Express, Python, React, Next.js, PostgreSQL, pgvector, Mastra, Claude API, OpenAI, local models via LM Studio, Lovable, Vercel, Figma

**Languages** · Swedish and English (native), Tigrinya and Arabic (B2)

farre@holgerai.com
