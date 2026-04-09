<!-- ZAYVORA // DAXINI STACK // README v2.0.77 -->

```
███████╗ █████╗ ██╗   ██╗██╗   ██╗ ██████╗ ██████╗  █████╗
╚══███╔╝██╔══██╗╚██╗ ██╔╝██║   ██║██╔═══██╗██╔══██╗██╔══██╗
  ███╔╝ ███████║ ╚████╔╝ ██║   ██║██║   ██║██████╔╝███████║
 ███╔╝  ██╔══██║  ╚██╔╝  ╚██╗ ██╔╝██║   ██║██╔══██╗██╔══██║
███████╗██║  ██║   ██║    ╚████╔╝ ╚██████╔╝██║  ██║██║  ██║
╚══════╝╚═╝  ╚═╝   ╚═╝     ╚═══╝   ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝
```

> **`// SYSTEM BOOT — LOCAL AI STACK INITIALIZING`**
> `>> CLOUD DEPENDENCY: 0.00%`
> `>> SOVEREIGNTY STATUS: ████████████ 100%`
> `>> LOCATION: YOUR OWN MACHINE`

---

<div align="center">

[![Ollama](https://img.shields.io/badge/Ollama-daxini2404%2Fzayvora-00FF9C?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZD0iTTEyIDJDNi40OCAyIDIgNi40OCAyIDEyczQuNDggMTAgMTAgMTAgMTAtNC40OCAxMC0xMFMxNy41MiAyIDEyIDJ6IiBmaWxsPSIjMDBGRjlDIi8+PC9zdmc+)](https://ollama.com/daxini2404/zayvora)
[![KDP Book 1](https://img.shields.io/badge/Amazon%20KDP-The%20Daxini%20Stack-%23FF2D55?style=for-the-badge&logo=amazon)](https://www.amazon.com/dp/B0F9WY9BW5)
[![KDP Book 2](https://img.shields.io/badge/Amazon%20KDP-daxini.space%20Handbook-%23FF2D55?style=for-the-badge&logo=amazon)](https://www.amazon.com/dp/B0F35351JP)
[![License](https://img.shields.io/badge/LICENSE-MIT-7B00FF?style=for-the-badge)](LICENSE)
[![RAM](https://img.shields.io/badge/RAM_REQUIRED-8GB-00BFFF?style=for-the-badge)]()
[![Cloud](https://img.shields.io/badge/CLOUD_REQUIRED-NONE-FF2D55?style=for-the-badge)]()

</div>

---

## `// JACK IN. NO CLOUD REQUIRED.`

**Zayvora** is a local-first AI reasoning engine built on quantized Llama 3 (Q4_0, 4.7GB). It doesn't autocomplete your questions. It **thinks through them** — running a structured 6-stage reasoning loop on your own hardware, fully offline, zero API keys, zero subscriptions, zero vendor lock-in.

It ran on a 14-hour flight from Delhi to London with no Wi-Fi.  
It will run the next time OpenAI goes down.  
It will run the day your cloud provider changes their terms of service.

```bash
ollama run daxini2404/zayvora
```

That's it. You're sovereign.

---

## `// THE 6-STAGE REASONING LOOP`

> Most AI autocompletes. Zayvora **reasons**.

```
┌─────────────────────────────────────────────────────────┐
│  ░░ ZAYVORA REASONING ENGINE v2.0 ░░                    │
│                                                         │
│  [01] DECOMPOSE  ──► Break question into sub-problems   │
│         │                                               │
│  [02] RETRIEVE   ──► Pull from Nex RAG (12,000+ books)  │
│         │                                               │
│  [03] SYNTHESIZE ──► Draft each sub-answer separately   │
│         │                                               │
│  [04] CALCULATE  ──► Track units. Flag inconsistencies. │
│         │                                               │
│  [05] VERIFY     ──► 3 tests. Fail = no output.         │
│         │                                               │
│  [06] REVISE     ──► Route back. Retry from failure.    │
│         │                                               │
│  OUTPUT: Verified answer — or honest uncertainty.       │
└─────────────────────────────────────────────────────────┘
```

The loop terminates on two conditions:
- ✅ All three verification checks pass
- 🔴 Explicit: *"I don't know, and here's exactly why"*

The second output is not a failure. It is the most honest thing a reasoning system can produce.

---

## `// THE STACK`

```
╔══════════════════════════════════════════════════════╗
║  THE DAXINI STACK — LOCAL AI ARCHITECTURE            ║
╠══════════════════════════════════════════════════════╣
║                                                      ║
║  ┌──────────────┐   ┌──────────────┐                 ║
║  │   ZAYVORA    │   │     NEX      │                 ║
║  │  Reasoning   │◄──│  RAG Engine  │                 ║
║  │   Engine     │   │ 12,000 Books │                 ║
║  └──────┬───────┘   └──────────────┘                 ║
║         │           Dense + Sparse + RRF             ║
║         ▼                                            ║
║  ┌──────────────┐   ┌──────────────┐                 ║
║  │   ORCHADE    │   │   STUDYOS    │                 ║
║  │  Asyncio     │──►│  Single HTML │                 ║
║  │  Orchestrat. │   │  No Framework│                 ║
║  └──────────────┘   └──────────────┘                 ║
║                                                      ║
║  CLOUD DEPENDENCIES: ████░░░░░░░░ ZERO               ║
╚══════════════════════════════════════════════════════╝
```

| Component | Role | Stack |
|-----------|------|-------|
| **Zayvora** | 6-stage reasoning engine | Llama 3 Q4_0 via Ollama |
| **Nex** | Hybrid RAG retrieval | ChromaDB + BM25 + nomic-embed-text |
| **Orchade** | Async runtime orchestration | Python asyncio, job queuing |
| **StudyOS** | Interface | Single HTML file. No build step. |

---

## `// NEX: THE RETRIEVAL ENGINE`

> 12,000 technical books. ~200ms query time. Zero cloud.

Standard keyword search (BM25) breaks at scale — vocabulary fragmentation, term frequency noise, retrieval lists that are technically correct and practically useless.

Nex solves it with **Hybrid Retrieval + Reciprocal Rank Fusion:**

```python
# The RRF formula that powers Nex
RRF(chunk) = Σ 1 / (k + rank_in_list)
# k = 60 (smoothing constant)
# Chunks appearing in BOTH ranked lists rise to the top
# Agreement between methods = signal
```

**Chunking strategy:**
```
Chunk size    : 512 tokens
Overlap       : 64 tokens  
Boundaries    : Sentence-level (spaCy)
Index         : Local ChromaDB instance
Embedding     : nomic-embed-text via Ollama
```

Everything stays on your machine. A question asked against a cloud-hosted RAG system **is a question that leaves the building.** Nex keeps it home.

---

## `// SYSTEM REQUIREMENTS`

```
MINIMUM HARDWARE
────────────────
RAM     : 8 GB
STORAGE : ~5 GB (model: 4.7GB)
NETWORK : NOT REQUIRED AT RUNTIME
GPU     : Optional — Apple Silicon Neural Engine recommended

TESTED ON
─────────
✓ Apple Silicon M-series (passive cooling, sustained load)
✓ 14-hour Delhi → London flight (0 Wi-Fi, 0 issues)
✓ "While OpenAI was down" (repeatedly)
```

---

## `// QUICKSTART`

```bash
# Step 1: Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# Step 2: Pull and run Zayvora
ollama run daxini2404/zayvora

# That's it. You're running a 6-stage reasoning loop
# on your own hardware. Welcome to sovereignty.
```

🔗 **Ollama Model Page:** [ollama.com/daxini2404/zayvora](https://ollama.com/daxini2404/zayvora)

---

## `// THE BOOKS — LIVE ON AMAZON`

The Daxini Stack is documented in two books. Not marketing copy. Real architecture decisions, real failures, real trade-offs.

---

### 📘 The Daxini Stack: Engineering a Local-First AI System — A Technical Memoir
**`$5.00 USD · Kindle eBook · ASIN: B0F9WY9BW5`**

The honest account. The decisions, the failures, the architecture that finally held. Every design choice that went into building a zero-dependency AI reasoning system from the ground up — including the ones that didn't work.

> *If you want to understand the **why** behind local-first AI engineering — start here.*

**🛒 [Buy on Amazon → B0F9WY9BW5](https://www.amazon.com/dp/B0F9WY9BW5)**

---

### 📗 The daxini.space Handbook: Build Sovereign. Deploy Local. Own Your Stack.
**`$9.99 USD · Kindle eBook + Hardcover · ASIN: B0F35351JP`**

The step-by-step manual. If the memoir is the story, this is the blueprint. The Spatial OS, LogicHub, and the complete deployment pipeline. Available as eBook and in hardcover for those who want it on their desk.

> *Everything you need to build what I built — not just understand it.*

**🛒 [Buy on Amazon → B0F35351JP](https://www.amazon.com/dp/B0F35351JP)**

---

### 📐 Analytical Chemistry: Errors, Statistics & Data Analysis
**`$4.99 USD · Kindle eBook · ASIN: B0GQ6YKVDL`**

A complete study guide with worked examples, statistical tables, and exam tips. Part of the Analytical Chemistry Series.

**🛒 [Buy on Amazon → B0GQ6YKVDL](https://www.amazon.com/dp/B0GQ6YKVDL)**

---

## `// WHY SOVEREIGN MATTERS`

```
THE PROBLEM WITH RENTING YOUR OWN INTELLIGENCE
───────────────────────────────────────────────
✗  You cannot audit the system prompt running against your data
✗  You cannot pin a model version without paying for a tier
✗  You cannot run it when the service is down
✗  You cannot run it in air-gapped environments
✗  You cannot run it at altitude, at sea, offline
✗  Terms of service can revoke your access overnight

THE DAXINI STACK
────────────────
✓  Zero external dependencies at runtime
✓  Every component is auditable end-to-end
✓  Model version is pinned by you, changed by you
✓  No single point of failure you don't control
✓  Runs today exactly as it ran on day one
✓  No supply chain update can break it
```

> **Sovereignty is not ideology. It's what reliable infrastructure looks like.**

---

## `// AUTHOR`

```
╔══════════════════════════════════════════╗
║  DHARAM DAXINI                           ║
║  Gandhidham · Kutch · Gujarat · Bharat   ║
╠══════════════════════════════════════════╣
║  WEB    → daxini.xyz                     ║
║  OLLAMA → ollama.com/daxini2404/zayvora  ║
║  APP    → logichub.app                   ║
╚══════════════════════════════════════════╝
```

---

## `// REPO NAME SUGGESTIONS`

Looking for a name for this repo? Here are options ranked by vibe:

| Name | Vibe |
|------|------|
| `zayvora` | Clean. Exactly what it is. |
| `daxini-stack` | Broad — covers the full architecture |
| `sovereign-stack` | Philosophy-forward. Hits the mission. |
| `local-first-ai` | SEO-friendly. Discoverable. |
| `nex-zayvora-orchade` | Technical. For engineers who want to know exactly what they're getting. |
| `daxini2404` | Personal brand namespace |

**Recommended:** `zayvora` for the model repo, `daxini-stack` for the monorepo if you open-source the full architecture.

---

## `// STAR THIS REPO`

If this stack made you think differently about AI ownership, cloud dependency, or what it means to build sovereign infrastructure:

**⭐ Star it. Fork it. Build on it.**

> *Build sovereign. Deploy local. Own your stack.*

---

<div align="center">

```
// END OF FILE — SYSTEM NOMINAL — ALL PROCESSES LOCAL
// zayvora v2.0 · daxini stack · © dharam daxini
// BUILD SOVEREIGN. DEPLOY LOCAL. OWN YOUR STACK.
```

</div>
