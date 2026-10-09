### Farre

Stockholm. I build AI agents, retrieval systems and the websites around them, and I run them in production on my own hardware. Founder of [HolgerAI](https://holgerai.com).

---

#### HolgerAI · retrofit autonomy for forklifts

HolgerAI is a Swedish deep tech company. It is building a kit, with its own hardware, designed to make the forklifts a warehouse already owns drive themselves. The software can ask for full throttle, but permission to move runs through a hardware gate that no software can open. Swedish patent application SE 2530598-8 (2025) and PCT application (2026). I designed and built the site.

[![holgerai.com](bilder/holgerai.jpg)](https://holgerai.com)

#### Open source

- **[agent-permit](https://github.com/farrebutterfly-rgb/agent-permit)** · a human approves one exact agent action from the phone before it happens. Claude Code hook and MCP server, approval over Telegram, single use and time limited, with a hash-chained audit log. Tested live in Claude Code.
- **[svenska-pii](https://github.com/farrebutterfly-rgb/svenska-pii)** · Swedish PII recognizers with check-digit validation (personnummer, samordningsnummer, orgnr, bankgiro, plusgiro, IBAN) and Presidio integration. The benchmark shows why: Presidio's default recognizers flag 44 % of ordinary invoice numbers, dates and build stamps and never label a Swedish identifier with its right type. Try the rules in the browser at [holgerai.com/grind](https://holgerai.com/grind).
- **[hub-minne](https://github.com/farrebutterfly-rgb/hub-minne)** · local RAG memory for my agent platform. TypeScript, Mastra, Express and PostgreSQL with pgvector. Hybrid search (vectors plus Postgres full text, fused with Reciprocal Rank Fusion), source weighting, and a Mastra agent answering with citations from a local Qwen model. Measured on a question set with known answers, the share of questions with the right fact in the top 5 went from 45 % with plain vector search to 77 %.

#### The platform, with its checks

The agent platform runs on Kubernetes (k3s) set up with Terraform, delivered with Argo CD, login and roles in Keycloak, Kyverno policies, Ansible hardening and Wazuh alerts. The results of every automated check, with raw output, are at [holgerai.com/plattform](https://holgerai.com/plattform) (in Swedish).

#### Products on top of the platform

- **[Relta](https://relta.app)** · AI accounting bureau for Swedish companies. Built so that agents do the bookkeeping and an authorized accountant reviews and signs off. Deployed on Vercel and Neon with Stripe, BankID and bank connection. A PKI certificate from Expisoft ties the organisation e-ID to the company registration number.
- **[Lexra](https://lexra.se)** · AI-driven law firm. Built so that agents draft and review and a licensed lawyer signs. Contract review scored 87 % recall and 100 % precision on our own test set.
- **[Wattvik](https://wattvik.com)** · co-founder. Monitoring of electronic component shortages and sourcing for B2B buyers.

#### Also

- **Regla**, a concept for automating paperwork in Swedish civil construction: design system in Figma (variables, 14 text styles, mobile and web screens) and a pitch deck with CAD-style drawings.

---

**Stack** · TypeScript, Node.js, Express, Python, React, Next.js, PostgreSQL, pgvector, Mastra, Claude API, OpenAI, local models via LM Studio, Kubernetes, Terraform, Argo CD, Lovable, Vercel, Figma

**Languages** · Swedish and English (native), Tigrinya and Arabic (B2)

farre@holgerai.com
