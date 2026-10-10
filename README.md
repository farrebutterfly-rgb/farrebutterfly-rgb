### Farre

Stockholm. I build AI agents, retrieval systems and the websites around them, and I run them in production on my own hardware. Founder of [HolgerAI](https://holgerai.com).

[![fail-closed, verified every night](https://img.shields.io/endpoint?url=https://storage.googleapis.com/holgerai-kontoret/kaosprov_badge.json)](https://holgerai.com/kontoret) The badge is written by a chaos test that runs on the platform every night at 04:30: it kills the PII gate on purpose, checks that every outbound call is denied while it is down, waits for it to come back on its own, checks that personal data is still stopped and clean text still passes, switches the emergency stop on and off, and checks that the event reached the SIEM. Nine steps. If one fails the badge turns red and I get it on my phone.

---

#### Fråga · ask the agent

An agent that answers questions about the platform and about my work, in Swedish or English, from published material only, with the sources under every answer. Gemini on Vertex AI in the EU, on Cloud Run, behind the same PII gate that protects the platform: paste a personnummer into the question and it is stopped in your browser before it is even sent, and again in the service if it gets that far. The answer is scanned before it leaves. Nothing is logged with content, there is a daily cap, and the service account has one role. Deployed with Terraform on an image digest. [holgerai.com/fraga](https://holgerai.com/fraga)

#### Grinden · the gate, in your browser

The Swedish personal data rules that sit in front of every outbound call from my agents, as a page that runs entirely in the browser with zero network calls. Paste a text, watch the stamp come down (STOPPAS or SLÄPPS), change the last digit of a hit and see the check digit fail, add a protected client name, try full-width digits. A terminal panel shows exactly what the agent sees in Claude Code when the hook blocks a call: exit 2, the reason, and the fingerprint the phone approval is bound to. The JavaScript port is tested against the Python original on 950 texts with identical hits, verdicts and masking, and the page runs 48 of them as a self test every time it loads. [holgerai.com/grind](https://holgerai.com/grind)

#### Kontoret · the agents at work, live

A small office where the people have been replaced by my agents: one desk per company, a phone that lights up when an action waits for my yes, a lamp by the door for the gate that checks all text before it leaves the house, and a button that lets you attack an agent and watch what the platform does about it. The numbers are real and fetched from the platform every five minutes; only counts leave the machine. [holgerai.com/kontoret](https://holgerai.com/kontoret)

#### HolgerAI · retrofit autonomy for forklifts

HolgerAI is a Swedish deep tech company. It is building a kit, with its own hardware, designed to make the forklifts a warehouse already owns drive themselves. The software can ask for full throttle, but permission to move runs through a hardware gate that no software can open. Swedish patent application SE 2530598-8 (2025) and PCT application (2026). I designed and built the site.

[![holgerai.com](bilder/holgerai.jpg)](https://holgerai.com)

#### Open source

- **[agent-permit](https://github.com/farrebutterfly-rgb/agent-permit)** · a human approves one exact agent action from the phone before it happens. Claude Code hook and MCP server, approval over Telegram, single use and time limited, with a hash-chained audit log, and an emergency stop (`agent-permit freeze on`, or `/freeze` from the phone) that blocks every call until a human releases it. Tested live in Claude Code.
- **[svenska-pii](https://github.com/farrebutterfly-rgb/svenska-pii)** · Swedish PII recognizers with check-digit validation (personnummer, samordningsnummer, orgnr, bankgiro, plusgiro, IBAN) and Presidio integration. The benchmark shows why: on 1,500 lookalike numbers (dates, OCR and build numbers, wrong check digits) Presidio's default recognizers flag 44 %, svenska-pii 2.5 %, and without Swedish recognizers no Swedish identifier gets its right type. Try the rules in the browser at [holgerai.com/grind](https://holgerai.com/grind).
- **[hub-minne](https://github.com/farrebutterfly-rgb/hub-minne)** · local RAG memory for my agent platform. TypeScript, Mastra, Express and PostgreSQL with pgvector. Hybrid search (vectors plus Postgres full text, fused with Reciprocal Rank Fusion), source weighting, and a Mastra agent answering with citations from a local Qwen model. Measured on a question set with known answers, the share of questions with the right fact in the top 5 went from 45 % with plain vector search to 77 %.

Both packages run CodeQL, pip-audit and a CycloneDX SBOM on every push, with Dependabot and a SECURITY.md for private vulnerability reports.

#### The platform, with its checks

The agent platform runs on Kubernetes (k3s) set up with Terraform, delivered with Argo CD, login and roles in Keycloak, Kyverno policies, Ansible hardening, Wazuh alerts, and Prometheus and Grafana on the gate's scan latency. The results of every automated check, with raw output, are at [holgerai.com/plattform](https://holgerai.com/plattform) (in Swedish), together with the [threat model](https://holgerai.com/plattform/hotmodell.html) (eleven threats, the control for each, the evidence, and what is still missing) and the [architecture decisions](https://holgerai.com/plattform/beslut.html) (ten decisions with context and consequences, including the ones that turned out wrong). When something goes wrong I write it up: [postmortem, 3 and 4 October 2026](https://holgerai.com/plattform/incident-2026-10-04.html), three calls blocked because the hook gave up after 3 seconds while the gate was still scanning. Nothing leaked, the timeout was wrong, and the fix is measured.

#### Products on top of the platform

- **[Relta](https://relta.app)** · AI accounting bureau for Swedish companies. Built so that agents do the bookkeeping and an authorized accountant reviews and signs off. Deployed on Vercel and Neon with Stripe, BankID and bank connection. A PKI certificate from Expisoft ties the organisation e-ID to the company registration number.
- **[Lexra](https://lexra.se)** · AI-driven law firm. Built so that agents draft and review and a licensed lawyer signs. Contract review scored 87 % recall and 100 % precision on our own test set.
- **[Wattvik](https://wattvik.com)** · co-founder. Monitoring of electronic component shortages and sourcing for B2B buyers.

#### Also

- **Regla**, a concept for automating paperwork in Swedish civil construction: design system in Figma (variables, 14 text styles, mobile and web screens) and a pitch deck with CAD-style drawings.

---

**Stack** · TypeScript, Node.js, Express, Python, React, Next.js, PostgreSQL, pgvector, Mastra, Claude API, OpenAI, Gemini on Vertex AI, local models via LM Studio, Kubernetes, Terraform, Argo CD, Google Cloud Run, Prometheus, Grafana, Wazuh, Lovable, Vercel, Figma

**Languages** · Swedish and English (native), Tigrinya and Arabic (B2)

farre@holgerai.com
