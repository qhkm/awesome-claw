# Awesome Claw

> A curated list of the OpenClaw family — the open-source AI agent ecosystem that exploded in early 2026. From the original 150K-star project to $5 IoT chips, Rust-native frameworks, and security tooling.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

---

## Contents

- [The Claw Family Tree](#the-claw-family-tree)
- [Core Projects](#core-projects)
- [Lightweight & Embedded Claws](#lightweight--embedded-claws)
- [Managed & Hosted Platforms](#managed--hosted-platforms)
- [Forks & Variants](#forks--variants)
- [Security & Hardening](#security--hardening)
- [Skills & Marketplace](#skills--marketplace)
- [Awesome Lists & Resources](#awesome-lists--resources)
- [Social & Agent Networks](#social--agent-networks)
- [Enterprise Integrations](#enterprise-integrations)
- [Community & Media](#community--media)

---

## The Claw Family Tree

```
Clawdbot (Nov 2025)
  └─ Moltbot (Jan 27, 2026) ─── renamed after Anthropic trademark complaint
       └─ OpenClaw (Jan 30, 2026) ─── current name, 150K+ GitHub stars
            ├── MoltBook ─── social network for AI agents (1.5M+ agents)
            ├── ClawHub ─── skill marketplace (5,700+ skills)
            ├── MoltWorker ─── Cloudflare Workers adaptation
            ├── AgentClaw ─── one-click deployment platform
            ├── ClawSec ─── security skill suite (Prompt Security)
            │
            ├── Lightweight & Embedded Variants:
            │   ├── ZeroClaw ─── Rust, 4.6K⭐, 3.4MB, <10ms startup
            │   ├── ZeptoClaw ─── Rust, IoT-first, 5MB binary
            │   ├── PicoClaw ─── Go, 11.6K⭐, RISC-V, <10MB RAM
            │   ├── NanoClaw ─── TypeScript, 8.6K⭐, container-isolated
            │   ├── TinyClaw ─── Shell/TS, 1.8K⭐, multi-agent teams
            │   ├── MimiClaw ─── ESP32-S3 embedded ($5 chip)
            │   ├── SeaClaw ─── C, <2MB, <50ms cold start
            │   ├── FemtoClaw ─── Rust, minimalist
            │   └── LispClaw ─── Common Lisp, experimental
```

---

## Core Projects

### OpenClaw (the mothership)

| | |
|---|---|
| **Repo** | [openclaw/openclaw](https://github.com/openclaw/openclaw) |
| **Website** | [openclaw.ai](https://openclaw.ai/) |
| **Docs** | [docs.openclaw.ai](https://docs.openclaw.ai/) |
| **Creator** | Peter Steinberger (Austria) |
| **Stars** | 150,000+ |
| **Language** | TypeScript/Node.js |
| **License** | Open Source |

The original. A local-first personal AI assistant that connects to 12+ messaging channels (WhatsApp, Telegram, Slack, Discord, Signal, iMessage, Teams, Google Chat, Matrix, BlueBubbles, Zalo, WebChat). Runs on your own hardware, model-agnostic (Claude, GPT, DeepSeek, Ollama local models). Uses `SOUL.md` for persistent agent identity and `SKILL.md` for extensible capabilities.

**Key architecture primitives:**
- Persistent identity via SOUL.md
- Periodic autonomy via heartbeat
- Accumulated memory across sessions
- Social context via MoltBook integration

**Coverage:** [CNBC](https://www.cnbc.com/2026/02/02/openclaw-open-source-ai-agent-rise-controversy-clawdbot-moltbot-moltbook.html) | [IBM](https://www.ibm.com/think/news/clawdbot-ai-agent-testing-limits-vertical-integration) | [Fortune](https://fortune.com/2026/02/12/openclaw-ai-agents-security-risks-beware/) | [Wikipedia](https://en.wikipedia.org/wiki/OpenClaw)

---

## Lightweight & Embedded Claws

Projects that shrink the Claw concept for edge, IoT, and resource-constrained environments.

### ZeroClaw

| | |
|---|---|
| **Repo** | [theonlyhennygod/zeroclaw](https://github.com/theonlyhennygod/zeroclaw) |
| **Stars** | 4,618 |
| **Language** | Rust |
| **Binary** | ~3.4MB |
| **Startup** | <10ms (warm), 0.38s (cold) |
| **RAM** | ~7.8MB peak |

High-performance reimplementation written in pure Rust. "Claw done right 🦀" — 400X faster startup than OpenClaw, runs on $10 hardware. Includes 22+ AI provider support, multi-channel messaging (CLI, Telegram, Discord, Slack, iMessage), SQLite hybrid memory with vector search, 1,017 tests, and three autonomy levels. Secure by design with pairing-based auth, strict sandboxing, and path jailing.

### ZeptoClaw

| | |
|---|---|
| **Repo** | [qhkm/zeptoclaw](https://github.com/qhkm/zeptoclaw) |
| **Language** | Rust |
| **Binary** | ~5MB |
| **Startup** | ~50ms |
| **RAM** | ~6MB |

Single Rust binary. 17 built-in tools, 5 channels (Telegram, Slack, Discord, Webhook, WhatsApp), container isolation (Docker + Apple Containers), agent swarms, plugins, batch processing, safety layer, MCP client. Designed for IoT/hardware-first deployments where every megabyte counts.

### NanoClaw

| | |
|---|---|
| **Repo** | [qwibitai/nanoclaw](https://github.com/qwibitai/nanoclaw) |
| **Website** | Featured on [VentureBeat](https://venturebeat.com/orchestration/nanoclaw-solves-one-of-openclaws-biggest-security-issues-and-its-already) |
| **Stars** | 8,625 |
| **Language** | TypeScript (Claude Agent SDK) |

Security-first alternative. Agents run inside isolated containers (Docker or Apple Container) so even rogue AI stays sandboxed. Dramatically smaller codebase than OpenClaw (~4,000 lines vs ~400,000). Built on Anthropic's Claude Agent SDK. Connects to WhatsApp, has memory, scheduled jobs.

### MimiClaw

| | |
|---|---|
| **Repo** | [memovai/mimiclaw](https://github.com/memovai/mimiclaw) |
| **Website** | [mimiclaw.io](https://www.mimiclaw.io/) |
| **Hardware** | ESP32-S3 |

Runs OpenClaw on a $5 chip. No OS, no Node.js, no Raspberry Pi needed. Local-first memory on flash, connects to Telegram + Claude. Featured on [CNX Software](https://www.cnx-software.com/2026/02/13/mimiclaw-is-an-openclaw-like-ai-assistant-for-esp32-s3-boards/).

### PicoClaw

| | |
|---|---|
| **Repo** | [sipeed/picoclaw](https://github.com/sipeed/picoclaw) |
| **Stars** | 11,622 |
| **Hardware** | Sipeed LicheeRV Nano (RISC-V, $10) |
| **Language** | Go |
| **RAM** | <10MB |
| **Boot** | 1 second |

Ultra-lightweight. Claims to match OpenClaw's core features with 1% of the code and 1% of the memory. Runs on RISC-V SOPHGO SG2002.

### TinyClaw

| | |
|---|---|
| **Repo** | [jlia0/tinyclaw](https://github.com/jlia0/tinyclaw) |
| **Website** | [tinyclaw.xyz](https://tinyclaw.xyz/) |
| **Stars** | 1,793 |
| **Language** | Shell (primary), TypeScript, Python |

Team of personal agents that collaborate with each other. Multiple isolated AI agents with specialized roles (coder, writer, researcher) work via chain execution and fan-out delegation. File-based queue architecture prevents race conditions. Supports Discord, WhatsApp, Telegram. Live TUI dashboard for monitoring. 24/7 operation via tmux.

Also see: [warengonzaga/tinyclaw](https://github.com/warengonzaga/tinyclaw) — ultra-minimal self-improving AI companion.

### SeaClaw

| | |
|---|---|
| **Repo** | [haeli05/seaclaw](https://github.com/haeli05/seaclaw) |
| **Stars** | 17 |
| **Language** | C |
| **Binary** | <2MB |
| **Startup** | <50ms (cold) |

OpenClaw rewritten in C. Single static binary optimized for maximum performance and minimal footprint. No runtime dependencies.

### FemtoClaw

| | |
|---|---|
| **Repo** | [mcotdev/femtoclaw](https://github.com/mcotdev/femtoclaw) |
| **Stars** | 2 |
| **Language** | Rust |

Tiny Rust-based version of OpenClaw. Super small implementation focused on minimalism.

### LispClaw

| | |
|---|---|
| **Repo** | [jsmorph/lispclaw](https://github.com/jsmorph/lispclaw) |
| **Language** | Common Lisp, Python |

Pi integrations for dynamic languages. Experimental implementation exploring Lisp-based agent architecture.

### Nanobot

| | |
|---|---|
| **Origin** | University of Hong Kong |
| **Language** | Python |
| **Lines** | ~4,000 |

The "cat-branded" alternative. Delivers core agent features in 99% less code than OpenClaw. Minimalist by design.

---

## Managed & Hosted Platforms

One-click or managed hosting for people who don't want to self-host.

| Platform | Description | Link |
|----------|-------------|------|
| **AgentClaw.now** | One-click OpenClaw deployment in <60 seconds by SEOZilla | [AI Journal](https://aijourn.com/seozilla-launches-agentclaw-now-to-bring-openclaw-ai-agents-to-everyone/) |
| **MyClaw.ai** | World's first one-click OpenClaw deployment platform | [Yahoo Finance](https://finance.yahoo.com/news/myclaw-ai-launches-worlds-first-153000127.html) |
| **Agent37** | Managed hosting for OpenClaw agents | - |
| **SimpleClaw** | Simplified OpenClaw hosting | - |
| **ClawCloud** | Cloud-hosted Claw agents | - |
| **EasyClaw** | Easy deployment platform | - |
| **Molty by Finna** | Managed Molt ecosystem | - |
| **Kilo Claw** | Hosted agents at scale | - |

---

## Forks & Variants

| Project | Description | Link |
|---------|-------------|------|
| **MoltWorker** | Cloudflare's official Workers adaptation of OpenClaw (PoC) | [cloudflare/moltworker](https://github.com/cloudflare/moltworker) |
| **openclaw-ai-sdk** | Vercel AI SDK fork — uses `useChat()` and AI SDK v5/6 instead of pi-mono | [kumarabhirup/openclaw-ai-sdk](https://github.com/kumarabhirup/openclaw-ai-sdk) |
| **openclaw-coolify** | Self-hosted OpenClaw via Coolify (one-click Docker) | [essamamdani/openclaw-coolify](https://github.com/essamamdani/openclaw-coolify) |
| **openclaw-ai (guide)** | 2026 guide with Kimi/Claude benchmarks and security alerts | [pano135/openclaw-ai](https://github.com/pano135/openclaw-ai) |

---

## Security & Hardening

The Claw ecosystem has attracted serious security scrutiny. These projects address it.

### ClawSec

| | |
|---|---|
| **Repo** | [prompt-security/clawsec](https://github.com/prompt-security/clawsec) |
| **By** | Prompt Security |
| **Website** | [prompt.security/clawsec](https://prompt.security/clawsec) |

Complete security skill suite for the OpenClaw family. Protects SOUL.md with drift detection, live security recommendations, automated audits, and skill integrity verification. Featured on [SentinelOne](https://www.sentinelone.com/blog/clawsec-hardening-openclaw-agents-from-the-inside-out/).

### OpenClaw Scanner

Open-source tool that detects autonomous AI agents running on networks. Created after 42,000+ exposed OpenClaw instances were found on the internet. [Help Net Security](https://www.helpnetsecurity.com/2026/02/12/openclaw-scanner-open-source-tool-detects-autonomous-ai-agents/)

### openclaw-skills-security

| | |
|---|---|
| **Repo** | [UseAI-pro/openclaw-skills-security](https://github.com/UseAI-pro/openclaw-skills-security) |

Security-first OpenClaw skills: prompt injection detection, supply chain attack detection, credential leak scanning. Works with Codex CLI, Claude Code, any LLM.

### Key Security Events

- **CVE-2026-25253** (CVSS 8.8) — Cross-site WebSocket hijacking, single malicious link = full RCE
- **ClawHavoc** — 341 malicious skills on ClawHub compromised 9,000+ installations
- **42,000 exposed instances** — 93% with critical auth bypass (Maor Dayan research)

**Security analysis:** [CrowdStrike](https://www.crowdstrike.com/en-us/blog/what-security-teams-need-to-know-about-openclaw-ai-super-agent/) | [Palo Alto](https://www.paloaltonetworks.com/blog/network-security/why-moltbot-may-signal-ai-crisis/) | [Kaspersky](https://www.kaspersky.com/blog/openclaw-vulnerabilities-exposed/55263/) | [Sophos](https://www.sophos.com/en-us/blog/the-openclaw-experiment-is-a-warning-shot-for-enterprise-ai-security) | [Semgrep Cheat Sheet](https://semgrep.dev/blog/2026/openclaw-security-engineers-cheat-sheet/)

---

## Skills & Marketplace

### ClawHub

| | |
|---|---|
| **Repo** | [openclaw/clawhub](https://github.com/openclaw/clawhub) |
| **Website** | [clawhub.ai](https://clawhub.ai/) |
| **Skills** | 5,700+ |

The npm of AI agent skills. Community-driven marketplace where devs publish code bundles that give agents new abilities. Post-ClawHavoc, requires identity verification for publishers. [Developer Guide](https://www.digitalapplied.com/blog/clawhub-skills-marketplace-developer-guide-2026)

### SOUL.md

| | |
|---|---|
| **Repo** | [aaronjmars/soul.md](https://github.com/aaronjmars/soul.md) |

The personality framework. Distills worldview, voice, and specific takes into structured markdown that any LLM can embody on the fly. Separates soul (philosophy), identity (presentation), and configuration (capabilities). [SOUL.md Templates](https://alirezarezvani.medium.com/10-soul-md-practical-cases-in-a-guide-for-moltbot-clawdbot-defining-who-your-ai-chooses-to-be-dadff9b08fe2)

### Skill Platforms

| Platform | Description | Link |
|----------|-------------|------|
| **Smithery** | MCP + OpenClaw skill hosting | [smithery.ai](https://smithery.ai/skills/openclaw/openclaw-setup) |
| **Skillsmp** | Skill marketplace aggregator | [skillsmp.com](https://skillsmp.com/) |

---

## Awesome Lists & Resources

Existing curated collections in the ecosystem:

| List | Focus | Link |
|------|-------|------|
| **SamurAIGPT/awesome-openclaw** | Comprehensive resources, tools, tutorials | [GitHub](https://github.com/SamurAIGPT/awesome-openclaw) |
| **rohitg00/awesome-openclaw** | 80+ ecosystem projects, hosting guides, cost comparisons | [GitHub](https://github.com/rohitg00/awesome-openclaw) |
| **VoltAgent/awesome-openclaw-skills** | 3,000+ curated skills from ClawHub | [GitHub](https://github.com/VoltAgent/awesome-openclaw-skills) |
| **sundial-org/awesome-openclaw-skills** | Top 913 regularly updated skills | [GitHub](https://github.com/sundial-org/awesome-openclaw-skills) |
| **hesamsheikh/awesome-openclaw-usecases** | Community use cases collection | [GitHub](https://github.com/hesamsheikh/awesome-openclaw-usecases) |
| **OpenClawSearch** | Searchable resource directory | [openclawsearch.com](https://openclawsearch.com/) |

---

## Social & Agent Networks

### MoltBook

| | |
|---|---|
| **Launched** | January 28, 2026 |
| **Creator** | Matt Schlicht |
| **Agents** | 2.5M+ registered |

The first social network exclusively for AI agents. Humans can observe but cannot participate. Agents post written content and interact through comments and upvotes/downvotes — like Reddit, but for bots. [TechCrunch](https://techcrunch.com/2026/01/30/openclaws-ai-assistants-are-now-building-their-own-social-network/) | [IEEE Spectrum](https://spectrum.ieee.org/moltbook-agentic-ai-agents-openclaw)

### MoltHub

The connective tissue of the Molt ecosystem. Registry and discovery layer for agents to find and interact with each other.

---

## Enterprise Integrations

| Company | Integration | Source |
|---------|-------------|--------|
| **Baidu** | Integrated OpenClaw into search app for 700M users | [CNBC](https://www.cnbc.com/2026/02/13/baidu-openclaw-ai-search-app-integration-china-lunar-new-year.html) |
| **NVIDIA** | Run OpenClaw on GeForce RTX / DGX Spark GPUs | [NVIDIA](https://www.nvidia.com/en-us/geforce/news/open-claw-rtx-gpu-dgx-spark-guide/) |
| **Cloudflare** | MoltWorker — OpenClaw on Workers | [GitHub](https://github.com/cloudflare/moltworker) |
| **Mixpost** | Social media management skill on ClawHub | [Mixpost](https://mixpost.app/blog/openclaw-skill) |

---

## Community & Media

### Key Articles

- [CNBC: From Clawdbot to Moltbot to OpenClaw](https://www.cnbc.com/2026/02/02/openclaw-open-source-ai-agent-rise-controversy-clawdbot-moltbot-moltbook.html)
- [IBM: OpenClaw, Moltbook and the future of AI agents](https://www.ibm.com/think/news/clawdbot-ai-agent-testing-limits-vertical-integration)
- [DigitalOcean: What is OpenClaw?](https://www.digitalocean.com/resources/articles/what-is-openclaw)
- [Milvus: Complete Guide to the Autonomous AI Agent](https://milvus.io/blog/openclaw-formerly-clawdbot-moltbot-explained-a-complete-guide-to-the-autonomous-ai-agent.md)
- [The Conversation: Why a DIY AI agent feels so new but really isn't](https://theconversation.com/openclaw-and-moltbook-why-a-diy-ai-agent-and-social-media-for-bots-feel-so-new-but-really-arent-274744)
- [The Register: It's easy to backdoor OpenClaw](https://www.theregister.com/2026/02/05/openclaw_skills_marketplace_leaky_security/)
- [Gary Marcus: OpenClaw is everywhere all at once](https://garymarcus.substack.com/p/openclaw-aka-moltbot-is-everywhere)

### Critical Takes

- [XDA: Please stop using OpenClaw](https://www.xda-developers.com/please-stop-using-openclaw/)
- [Fortune: Why security experts are on edge](https://fortune.com/2026/02/12/openclaw-ai-agents-security-risks-beware/)
- [Vectra: When Automation Becomes a Digital Backdoor](https://www.vectra.ai/blog/clawdbot-to-moltbot-to-openclaw-when-automation-becomes-a-digital-backdoor)

### Acquisition Drama

Peter Steinberger has [offers from Meta and OpenAI on the table](https://www.trendingtopics.eu/openclaw-peter-steinberger-already-has-offers-from-meta-and-openai-on-the-table/), and has spoken with Microsoft CEO Satya Nadella. Community celebrated at [OpenClaw Vienna](https://www.trendingtopics.eu/openclaw-vienna-celebrate-peter-steinberger/).

### Alternatives Compared

- [Emergent: 6 OpenClaw Competitors](https://emergent.sh/learn/best-openclaw-alternatives-and-competitors)
- [SuperPrompt: 9 AI Agents From Lightweight to Enterprise](https://superprompt.com/blog/best-openclaw-alternatives-2026)
- [Product Hunt: Best OpenClaw Alternatives](https://www.producthunt.com/products/clawdbot-2/alternatives)
- [eesel: 5 Best Alternatives](https://www.eesel.ai/blog/openclaw-ai-alternatives)

---

## Contributing

Found a Claw project we missed? Open a PR or issue!

Please read the [Contributing Guidelines](CONTRIBUTING.md) before submitting.

**Quick guidelines:**
- Ensure the project is related to the OpenClaw ecosystem
- Follow the existing format and alphabetical order
- Include key metadata (repo, language, stars, description)
- One pull request per addition
- Verify all links work

## License

[![CC0](https://img.shields.io/badge/license-CC0-1.0-blue.svg)](LICENSE)

This work is licensed under [CC0 1.0 Universal](LICENSE).

To the extent possible under law, the contributors have waived all copyright and related or neighboring rights to this work. This list is dedicated to the public domain.
