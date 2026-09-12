<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=2800&pause=1200&color=378ADD&center=true&vCenter=true&width=760&lines=Samuel+Oral+Robert+V;Python+Developer+%7C+AI+Agents+%7C+Backend;Build+%E2%86%92+Test+%E2%86%92+Break+%E2%86%92+Debug+%E2%86%92+Measure)](https://github.com/leumaslarotrebor)

**Building reliable AI systems — from tool execution and evaluation to the infrastructure underneath.**

[![Portfolio](https://img.shields.io/badge/Portfolio-leumaslarotrebor.github.io-0a2040?style=flat-square)](https://leumaslarotrebor.github.io)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/samuel-oral-robert-v-4226813a4/)
[![IEEE](https://img.shields.io/badge/IEEE_ICIPCN_2026-Published-00629B?style=flat-square&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11438485)

</div>

<br>

<table>
<tr>
<td width="58%" valign="top">

### What I actually build

2026 Computer Science Engineering graduate. I write Python systems and test them against their failure
paths, not just their happy paths.

- **Python** — typed, validated backend services (FastAPI + Pydantic), not scripts
- **AI agents** — real tool calling, policy-grounded decisions, human approval gates
- **Testing** — scenario-based pytest suites that cover failure modes on purpose
- **Debugging & reliability** — idempotency, defense-in-depth validation, no silent failures
- **Linux** — process/service monitoring, auto-remediation, `/proc`, `systemctl`
- **Docker** — Dockerfiles + Compose stacks for local multi-container runs
- **Fundamentals** — a hand-built compiler pipeline (lexer → parser → AST → interpreter)

</td>
<td width="42%" align="center">

<img src="pixel_scene_small.gif" width="100%" alt="animated pixel scene" />

<sub>Chennai, India → open to relocation </sub>

</td> 
</tr>
</table>

---

## Featured: AgentResolve

**An agent that doesn't just answer — it looks things up, decides, and acts.**

Given a natural-language support request, it plans a sequence of tool calls, grounds its
decision in retrieved policy, and executes a real (mock) business action through typed,
validated Python tools — pausing for human approval when the action is consequential enough
to require it.

```text
Customer request
       ↓
Context retrieval        get_customer, get_order
       ↓
Policy grounding         search_knowledge_base (not a keyword guess)
       ↓
Tool selection            8 typed tools, chosen at runtime — no hardcoded if/else
       ↓
Authorization gate         refund ≥ threshold → pause, request human approval
       ↓
Tool execution             create_replacement / create_refund / create_support_ticket
       ↓
Validation                 every tool result's `success` field is checked, never assumed
       ↓
Audit                      step + tool-call event appended to an append-only trail
       ↓
Resolution / Escalation    autonomous close-out, or handed to a human — never a false success
```

| | |
|---|---|
| 🐍 Python backend | FastAPI + Pydantic v2, 8 typed tools behind a single registry, no database — local JSON store by design |
| 🧠 Tool calling | Real Anthropic tool calling, with a deterministic offline fallback so it runs and tests without an API key |
| ✅ Human-in-the-loop | Refunds above threshold cannot execute without explicit approval — enforced twice (planner + tool-level defense in depth) |
| 🔁 Idempotent | Duplicate requests never double-create an action; a failed tool call is never reported as a success |
| 🧪 Tested | **38/38 pytest tests passing** — re-run and verified directly, covering happy paths *and* failure modes (unknown customer, out-of-stock, expired window, suspended account, duplicate execution, invalid tool args) |
| 🖥️ Full stack | FastAPI backend, React + TypeScript dashboard (`tsc -b && vite build` — clean build, verified), Docker Compose |

**[→ github.com/leumaslarotrebor/agentresolve](https://github.com/leumaslarotrebor/agentresolve)**

---

## Other Projects

### 🖥️ [InfraWatch](https://github.com/leumaslarotrebor/infrawatch) — Linux Monitoring & Auto-Remediation
`Python` `Bash` `Docker` `Ansible` `Prometheus` `Grafana` `GitHub Actions`

**Problem:** service failures on a Linux host go unnoticed until someone checks manually.
**Solution:** a monitor script that reads `/proc/stat` and `/proc/meminfo` directly, checks
disk via `df` and DNS via `dig`, detects service failures via `systemctl is-active`, and
auto-restarts + re-verifies recovery — every 30 seconds, with incident logs and a Prometheus
`/metrics` endpoint. The full stack (agent + Prometheus + Grafana) is provisioned with an
Ansible playbook; a GitHub Actions CI workflow runs on every push.

### 🔤 [SamLang](https://github.com/leumaslarotrebor/samlang) — A Programming Language From Scratch
`Python` `Compiler Design` `Lexer` `Parser` `AST` `Interpreter`

**Problem:** using a language isn't the same as understanding one.
**Solution:** a full pipeline — handwritten lexer, recursive-descent parser, AST, tree-walking
interpreter — with lexical scoping and recursion, built to answer "what actually happens
between source code and execution?"

```text
source.sam → Lexer → tokens → Parser → AST → Interpreter → output
```

### 🧠 [DocuMind](https://github.com/leumaslarotrebor/documind) — RAG Document Intelligence
`Python` `FastAPI` `FAISS` `sentence-transformers` `Docker`

**Problem:** keyword search misses relevant passages that don't share exact wording.
**Solution:** PDF → chunking → `all-MiniLM-L6-v2` embeddings → FAISS vector index → top-k
semantic search, served through a FastAPI upload/query API.

### 📊 [Data Audit Pipeline](https://github.com/leumaslarotrebor/data-audit-pipeline) — Data Quality & Analytics
`Python` `pandas` `FastAPI` `PostgreSQL`

**Problem:** "check for nulls and duplicates" is a narrow slice of what data quality work
actually is.
**Solution:** an end-to-end Python pipeline — profiling, a 5-dimension data-quality scoring
framework, transformation into PostgreSQL, and statistical/funnel analysis on top — built on
top of what started as a simple null/duplicate audit script.

### 🌾 [SmartFarmX](https://github.com/leumaslarotrebor/smartfarmx) — IEEE-Published Precision Agriculture
`ESP32` `C++` `Python` `TensorFlow` `OpenCV` `Arduino` `IoT`

**Problem:** commercial precision-agriculture tooling is priced out of reach for small farms.
**Solution:** a drone for aerial crop-disease detection (TensorFlow/OpenCV) paired with an
ESP32 ground rover for soil monitoring, running in SoftAP mode — no router, no cloud, no
subscription.
📄 [IEEE ICIPCN 2026 paper →](https://ieeexplore.ieee.org/document/11438485)

---

## Verified Metrics

*Independently re-run, or pulled directly from repository source — nothing here is estimated.*

| Project | Metric | How it was verified |
|---|---|---|
| AgentResolve | 38/38 pytest tests passing | Re-ran `pytest -v` directly against the current commit |
| AgentResolve | 8 typed tools | Counted in `app/tools/registry.py` |
| AgentResolve | Clean TypeScript build | Re-ran `tsc -b && vite build` directly — no errors |
| InfraWatch | 5 checks every 30s (CPU, memory, disk, DNS, service) | Read directly from `scripts/monitor.sh` |
| InfraWatch | CI on every push | Live `.github/workflows/ci.yml` in the repo |
| SmartFarmX | 90.3% crop-disease detection · 92% nutrient classification · 15–18% fertilizer reduction · ₹28,000 build cost | As documented in the published IEEE paper / repo README |

---

## How I Think About Engineering

```text
Build → Test → Break → Debug → Measure → Improve
```

Concretely: decisions grounded in retrieved data rather than guesses, tool results validated
before they're trusted, and failure paths — out-of-stock, expired windows, suspended
accounts, unknown records, service crashes — treated as first-class test scenarios, not
afterthoughts. Every project above documents what's real versus simulated rather than
rounding up.

---

## Tech Stack

<table>
<tr><td valign="top">

**Languages**
<br>Python · Java · JavaScript/TypeScript
<br>SQL · Bash · C/C++

</td><td valign="top">

**AI / ML**
<br>LLM tool calling · AI agents
<br>RAG · TensorFlow · scikit-learn

</td><td valign="top">

**Backend**
<br>FastAPI · REST · PostgreSQL
<br>Pydantic

</td></tr>
<tr><td valign="top">

**Infrastructure**
<br>Linux · Docker · Docker Compose
<br>Ansible · Prometheus · Grafana · GitHub Actions

</td><td valign="top">

**Testing**
<br>pytest · unit & integration testing
<br>scenario/failure-mode testing · debugging

</td><td valign="top">

</td></tr>
</table>

<div align="center">

[![My Skills](https://skillicons.dev/icons?i=python,cpp,js,ts,bash,fastapi,react,nodejs,docker,ansible,prometheus,postgres,linux,git,github,arduino,tensorflow&perline=9)](https://skillicons.dev)

</div>

---

## Research

**SmartFarmX**, published at IEEE ICIPCN 2026, is evidence of engineering across the full
stack: embedded firmware on ESP32, computer-vision-based disease detection, sensor data
ingestion, and building a system that has to work under real-world field constraints
(no internet, tight budget) rather than in a clean demo environment.

---

<div align="center">

**[Portfolio](https://leumaslarotrebor.github.io) · [LinkedIn](https://linkedin.com/in/samuel-oral-robert-v-4226813a4/) · [GitHub](https://github.com/leumaslarotrebor) · samueloralrobert1234@gmail.com**

</div>
