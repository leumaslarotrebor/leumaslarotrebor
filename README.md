<div align="center">

# Samuel Oral Robert V

**IoT & AI Systems Engineer · Backend · Embedded · Precision Agriculture**

[![Portfolio](https://img.shields.io/badge/Portfolio-leumaslarotrebor.github.io-0a2040?style=for-the-badge&logo=github&logoColor=white)](https://leumaslarotrebor.github.io)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/samuel-oral-robert-v-4226813a4/)
[![IEEE](https://img.shields.io/badge/IEEE-Published_ICIPCN_2026-00629B?style=for-the-badge&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11438485)

</div>

---

## About

I build systems that work in the real world.

From ESP32 firmware running autonomously in crop fields, to Linux auto-remediation agents that detect and fix failures without human intervention, to RAG pipelines that make documents queryable — my work is about systems that are reliable, deployable, and solve real problems.

My IEEE-published research on IoT precision agriculture (ICIPCN 2026) is the clearest example of how I work: identify a real problem, build a complete system end-to-end, validate it in the field, and publish the results.

---

## Projects

### SmartFarmX — IEEE Published Precision Agriculture System
> ESP32 · C++ · Python · TensorFlow · OpenCV · Arduino

Two-component IoT system for precision agriculture. A drone handles aerial crop spraying and disease detection (90.3% accuracy). A ground rover monitors soil moisture in real time with zero internet dependency — it broadcasts its own WiFi so a farmer can connect directly from a phone browser in the middle of a field.

**Published at IEEE ICIPCN 2026** → [Paper](https://ieeexplore.ieee.org/document/11438485) · [Code](https://github.com/leumaslarotrebor/smartfarmx)

---

### SamLang — Custom Programming Language
> Python · Compiler Design · Lexer · Parser · AST · Interpreter

Built a fully functional programming language from scratch. Handwritten lexer, recursive-descent parser, AST node system, and tree-walking interpreter with lexical scoping and recursion. Supports variables, arithmetic, conditionals, while loops, and user-defined functions.
fun factorial(n) {

if n <= 1 { return 1 }

return n * factorial(n - 1)

}

print factorial(6)   # → 720

[Code](https://github.com/leumaslarotrebor/samlang)

---

### InfraWatch — Linux Health Monitor & Auto-Remediation
> Python · Bash · Docker · Ansible · Prometheus · Grafana · GitHub Actions

Real-time Linux health monitoring agent that reads `/proc/stat` and `/proc/meminfo`, detects downed services, triggers `systemctl restart`, verifies recovery, and writes structured incident logs. Exposes Prometheus-compatible `/metrics` and `/health` endpoints. Full stack provisioned via Ansible. CI pipeline runs shellcheck, flake8, ansible-lint on every push.

[Code](https://github.com/leumaslarotrebor/infrawatch)

---

### DocuMind — RAG Document Intelligence
> Python · FastAPI · FAISS · sentence-transformers · Docker

Upload a PDF, ask questions in natural language, get context-aware answers using semantic search and sentence embeddings. No keyword matching — the system finds contextually relevant passages using FAISS vector search and all-MiniLM-L6-v2 embeddings.

[Code](https://github.com/leumaslarotrebor/documind)

---

### Data Audit Pipeline
> Python · FastAPI · PostgreSQL · pandas

Automated data quality audit system — schema validation, null-check profiling, anomaly flagging, and audit trail generation across CSV and database sources. Exposes structured JSON reports via FastAPI endpoints with compliance-ready logs.

[Code](https://github.com/leumaslarotrebor/data-audit-pipeline)

---

## Stack
Languages   Python · C/C++ · JavaScript · SQL · Bash

Backend     FastAPI · Node.js · REST APIs

DevOps      Docker · Prometheus · Grafana · Ansible · GitHub Actions

AI/ML       FAISS · sentence-transformers · TensorFlow · OpenCV

Embedded    ESP32 · Arduino · MQTT · SoftAP WiFi

Databases   PostgreSQL · MongoDB · SQLite

---

## Publication

**Smart FarmX: Multipurpose Drone for Next-Generation Crop Monitoring & Optimization System using IoT**
Shagana S, Samuel Oral Robert V, Dr. Saranya S
*IEEE ICIPCN 2026 · Pages 729–735*
[https://ieeexplore.ieee.org/document/11438485](https://ieeexplore.ieee.org/document/11438485)

---

<div align="center">

**B.E. Computer Science Engineering · Sathyabama Institute of Science and Technology · Chennai · 2026**

*Open to backend, IoT, AI engineering, and international internship opportunities*

</div>
