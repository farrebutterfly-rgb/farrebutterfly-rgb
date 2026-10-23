### Farre

Stockholm. I build AI agents for regulated work, where personal data must never leak and a human approves before anything leaves the system. Founder of [HolgerAI](https://holgerai.com).

[![fail-closed, verified every night](https://img.shields.io/endpoint?url=https://storage.googleapis.com/holgerai-kontoret/kaosprov_badge.json)](https://holgerai.com/kontoret) A chaos test kills my PII gate every night at 04:30 and checks that every outbound call is denied until it comes back. Nine steps. If one fails, the badge turns red and my phone rings.

#### Try it live

| | |
|---|---|
| **[Kontoret](https://holgerai.com/kontoret)** | My agents at work, one desk per company, real numbers every five minutes. Attack an agent and watch the platform stop it. |
| **[Fråga](https://holgerai.com/fraga)** | Ask about my work in Swedish or English. Sources under every answer, and a personnummer is stopped in your browser before it is sent. |
| **[Grinden](https://holgerai.com/grind)** | The Swedish PII rules in the browser, zero network calls. Change a check digit and watch the verdict flip. |

#### Open source

- **[svenska-pii](https://github.com/farrebutterfly-rgb/svenska-pii)** · Swedish PII recognizers with check-digit validation for Presidio. On 1,500 lookalike numbers, Presidio's defaults flag 44 %, svenska-pii 2.5 %.
- **[agent-permit](https://github.com/farrebutterfly-rgb/agent-permit)** · A human approves one exact agent action from the phone. Claude Code hook and MCP server, hash-chained audit log, emergency stop.
- **[hub-minne](https://github.com/farrebutterfly-rgb/hub-minne)** · Local RAG memory with hybrid search and RRF. Right fact in the top 5 went from 45 % to 77 % on a fixed question set.

CodeQL, pip-audit and a CycloneDX SBOM on every push.

#### How the platform is run

Kubernetes with Terraform, Argo CD, Keycloak, Kyverno and Wazuh. Every check with raw output, the [threat model](https://holgerai.com/plattform/hotmodell.html), the [architecture decisions](https://holgerai.com/plattform/beslut.html) and a [postmortem](https://holgerai.com/plattform/incident-2026-10-04.html) are public at [holgerai.com/plattform](https://holgerai.com/plattform).

#### Products in development

- **[Relta](https://relta.app)** · AI accounting for businesses of every size. Agents do the bookkeeping, an authorised accountant signs with BankID.
- **[Lexra](https://lexra.se)** · AI legal work where a licensed lawyer signs. Contract review: 87 % recall, 100 % precision on our own test set.
- **[HolgerAI](https://holgerai.com)** · A retrofit kit that makes existing forklifts drive themselves, with a hardware gate no software can open. Patent pending (SE and PCT).

**Stack** · TypeScript, Python, Node.js, Next.js, PostgreSQL with pgvector, Claude, OpenAI, Gemini on Vertex AI, local Qwen, Kubernetes, Terraform, Cloud Run, Prometheus, Grafana

farre@holgerai.com
