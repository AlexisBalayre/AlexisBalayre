<div align="center">

<img width="100%" src="assets/header.svg" alt="Alexis Balayre, AI Engineer specialising in real-time speech AI" />

<p>
  <a href="https://alexis.balayre.com/"><img src="https://img.shields.io/badge/Portfolio-13327a?style=for-the-badge&logo=vercel&logoColor=white" alt="portfolio" /></a>
  <a href="https://linkedin.com/in/alexis-balayre"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0id2hpdGUiPjxwYXRoIGQ9Ik0yMC40NSAyMC40NWgtMy41NnYtNS41N2MwLTEuMzMtLjAzLTMuMDQtMS44NS0zLjA0LTEuODYgMC0yLjE0IDEuNDUtMi4xNCAyLjk0djUuNjdIOS4zNVY5aDMuNDF2MS41NmguMDVjLjQ4LS45IDEuNjQtMS44NSAzLjM3LTEuODUgMy42IDAgNC4yNyAyLjM3IDQuMjcgNS40NnY2LjI4ek01LjM0IDcuNDNhMi4wNyAyLjA3IDAgMSAxIDAtNC4xMyAyLjA3IDIuMDcgMCAwIDEgMCA0LjEzek03LjEyIDIwLjQ1SDMuNTZWOWgzLjU2djExLjQ1ek0yMi4yMiAwSDEuNzdDLjggMCAwIC43OCAwIDEuNzN2MjAuNTRDMCAyMy4yMi44IDI0IDEuNzcgMjRoMjAuNDVjLjk4IDAgMS43OC0uNzggMS43OC0xLjczVjEuNzNDMjQgLjc4IDIzLjIgMCAyMi4yMiAweiIvPjwvc3ZnPgo=" alt="linkedin" /></a>
  <a href="mailto:alexis@balayre.com"><img src="https://img.shields.io/badge/Email-1e56a0?style=for-the-badge&logo=gmail&logoColor=white" alt="email" /></a>
  <img src="https://komarev.com/ghpvc/?username=AlexisBalayre&label=Profile%20views&color=1e56a0&style=for-the-badge" alt="profile views" />
</p>

</div>

---

AI Engineer specialising in real-time speech AI, with a dual background in software engineering and data science. At [Acolad](https://www.acolad.com/) I build and run [Lia Live AI](https://www.acolad.com/en/lia/live), our AI interpreting platform: speech in, interpreted speech out in under a second, across 80+ languages. I own it end to end, from applied speech research and model evaluation to the production infrastructure behind live sessions. Beyond speech I work on agentic systems, LLM and RAG applications, and applied ML, turning prototypes into production. Lately a lot of that work has turned inward: open-source tooling that makes coding agents reviewable, so you still master a codebase that agents are writing. I care about AI security: as these systems take on more autonomy and more sensitive data, making them trustworthy matters as much as making them capable.

## 🧭 What I work on

- 🎙️ **Real-time speech AI:** streaming ASR, LLM translation and TTS, with the latency engineering to keep the whole pipeline under a second
- 🤖 **Agentic systems & LLM apps:** tool and function calling, RAG and GraphRAG, translation grounded in conversation history and client glossaries
- 🛠️ **Agentic coding infrastructure:** orchestrating parallel coding sessions, worktree isolation, deterministic hooks and multi-agent review — the guardrails that keep generated code reviewable
- 📏 **Evaluation:** frameworks that settle model and provider choices on quality and latency, benchmarked against human baselines
- ⚙️ **Production AI:** distributed backends, multi-provider routing, observability and cost attribution on Kubernetes

> 🔭 Currently going deeper on speech model fine-tuning, inference optimisation, and on-device deployment.

## 📌 Featured projects

### Agentic coding toolchain

Three layers of the same problem: agents write faster than humans review.

| Project | What it is | Stack |
| :--- | :--- | :--- |
| **[Pupitre](https://github.com/AlexisBalayre/pupitre)** | Control plane for running many Claude Code sessions in parallel: one git worktree per agent, a conflict radar, and a merge gate that blocks on build, tests, scope violations and technical-debt deltas. Every merge writes a decision record, so the code your agents write stays code you can explain. | `TypeScript` `Claude Code` `tmux` |
| **[agent-init](https://github.com/AlexisBalayre/agent-init)** | One agent setup for five tools (Claude Code, Codex, opencode, Mistral Vibe, Cursor). Conventions, skills and blocking hooks live once in `.agents/`; a per-tool adapter speaks each host's protocol, and `doctor` proves the block actually landed. | `TypeScript` `Node` `Shell` |
| **[claude-code-config](https://github.com/AlexisBalayre/claude-code-config)** | Drop-in Claude Code config for any repo: path-scoped rules, 34 skills, 12 subagents, 7 zero-token hooks, and a multi-agent PR review running in GitHub Actions with no model write channel to the PR. Stack-agnostic — `/adapt-to-project` fits it to the codebase. | `Claude Code` `GitHub Actions` `Shell` |

### AI systems & research

| Project | What it is | Stack |
| :--- | :--- | :--- |
| **[AI Daily Summary](https://github.com/AlexisBalayre/ai-daily-summary)** | Self-hosted pipeline that reads the day's AI news for you: ingests newsletters, RSS, GitHub and web crawls, summarises with an LLM, deduplicates by vector similarity, and sends a daily email with audio briefing. Queryable via chat API and MCP server. | `Python` `FastAPI` `pgvector` `MCP` |
| **[AuraHelpdeskGraph](https://github.com/AlexisBalayre/AuraHelpdeskGraph)** | Support chatbot answering from a company's own past tickets. Vector search plus a Neo4j graph to follow links between related tickets, local models so no data leaves the network, retrieval only when the question needs it. | `Python` `Neo4j` `Ollama` |
| **[RagDocs](https://github.com/AlexisBalayre/RagDocs)** | Private, API-free RAG over technical documentation with Milvus vector search and local LLMs. | `Python` `Milvus` `LlamaIndex` |
| **[Aircraft Refuelling Prediction](https://github.com/AlexisBalayre/future-position-prediction-for-aircraft-refueling)** | Master's thesis with Airbus: real-time computer vision that tracks an aircraft's fuel port and predicts its motion for autonomous refuelling, YOLOv10 detection plus a custom GRU sequence model, down to 2.15% error. | `PyTorch` `OpenCV` `YOLOv10` |

## 🛠️ Tech & Tools

<div align="center">

![Claude Code](https://img.shields.io/badge/Claude%20Code-D97757?style=for-the-badge&logo=anthropic&logoColor=white) ![Deepgram](https://img.shields.io/badge/Deepgram-13EF93?style=for-the-badge&logo=deepgram&logoColor=black) ![LiveKit](https://img.shields.io/badge/LiveKit-1B1B1F?style=for-the-badge&logo=livekit&logoColor=white) ![Gradium](https://img.shields.io/badge/Gradium-0A2540?style=for-the-badge&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white) ![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black) ![vLLM](https://img.shields.io/badge/vLLM-1e56a0?style=for-the-badge&logo=vllm&logoColor=white) ![Ollama](https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white) ![Gemini](https://img.shields.io/badge/Gemini-1A73E8?style=for-the-badge&logo=googlegemini&logoColor=white) ![OpenAI](https://img.shields.io/badge/OpenAI-13327a?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0id2hpdGUiPjxwYXRoIGQ9Ik0yMi4yOCA5LjgyYTUuOTggNS45OCAwIDAgMC0uNTItNC45MSA2LjA1IDYuMDUgMCAwIDAtNi41MS0yLjlBNi4wNyA2LjA3IDAgMCAwIDQuOTggNC4xOGE1Ljk5IDUuOTkgMCAwIDAtNCAyLjkgNi4wNSA2LjA1IDAgMCAwIC43NSA3LjEgNS45OCA1Ljk4IDAgMCAwIC41MSA0LjkgNi4wNSA2LjA1IDAgMCAwIDYuNTEgMi45QTUuOTggNS45OCAwIDAgMCAxMy4yNiAyNGE2LjA2IDYuMDYgMCAwIDAgNS43Ny00LjIgNS45OSA1Ljk5IDAgMCAwIDQtMi45IDYuMDYgNi4wNiAwIDAgMC0uNzUtNy4wOHpNMTMuMjYgMjIuNDNhNC40OCA0LjQ4IDAgMCAxLTIuODgtMS4wNGwuMTQtLjA4IDQuNzgtMi43NmEuOC44IDAgMCAwIC40LS42OHYtNi43NGwyLjAyIDEuMTdhLjA3LjA3IDAgMCAxIC4wNC4wNXY1LjU4YTQuNSA0LjUgMCAwIDEtNC41IDQuNXpNMy42IDE4LjNhNC40NyA0LjQ3IDAgMCAxLS41My0zLjAxbC4xNC4wOCA0Ljc4IDIuNzZhLjc3Ljc3IDAgMCAwIC43OCAwbDUuODQtMy4zN3YyLjMzYS4wOC4wOCAwIDAgMS0uMDMuMDZsLTQuODMgMi43OWE0LjUgNC41IDAgMCAxLTYuMTQtMS42NHpNMi4zNCA3LjlhNC40OSA0LjQ5IDAgMCAxIDIuMzctMS45OHY1LjY5YS43Ny43NyAwIDAgMCAuMzkuNjhsNS44MSAzLjM1LTIuMDIgMS4xN2EuMDguMDggMCAwIDEtLjA3IDBsLTQuODMtMi43OUE0LjUgNC41IDAgMCAxIDIuMzQgNy45em0xNi42IDMuODVsLTUuODQtMy4zOSAyLjAyLTEuMTZhLjA4LjA4IDAgMCAxIC4wNyAwbDQuODMgMi43OWE0LjQ5IDQuNDkgMCAwIDEtLjY4IDguMXYtNS42OGEuNzkuNzkgMCAwIDAtLjQtLjY2em0yLjAxLTMuMDJsLS4xNC0uMDktNC43Ny0yLjc4YS43OC43OCAwIDAgMC0uNzkgMEw5LjQxIDkuMjNWNi45YS4wNy4wNyAwIDAgMSAuMDMtLjA2bDQuODMtMi43OWE0LjUgNC41IDAgMCAxIDYuNjggNC42NnpNOC4zMSAxMi44NmwtMi4wMi0xLjE2YS4wOC4wOCAwIDAgMS0uMDQtLjA2VjYuMDdhNC41IDQuNSAwIDAgMSA3LjM4LTMuNDVsLS4xNC4wOC00Ljc4IDIuNzZhLjguOCAwIDAgMC0uNC42OHptMS4xLTIuMzdsMi42LTEuNSAyLjYgMS41djNsLTIuNiAxLjUtMi42LTEuNXoiLz48L3N2Zz4K) ![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white) ![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=for-the-badge&logo=nodedotjs&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-0db7ed?style=for-the-badge&logo=docker&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326ce5?style=for-the-badge&logo=kubernetes&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-FF4438?style=for-the-badge&logo=redis&logoColor=white) ![OpenSearch](https://img.shields.io/badge/OpenSearch-005EB8?style=for-the-badge&logo=opensearch&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white) ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

</div>

## 🎓 Background

Dual Master's in Computational Intelligence for Data Analytics ([Cranfield University](https://www.cranfield.ac.uk/courses/taught/computational-intelligence-for-data-analytics)) and Data Intelligence ([ISEP, Paris](https://en.isep.fr/studying-at-isep/isep-engineering-master-degree/)). At Dassault Systèmes I applied NLP and generative AI (topic modelling, sentiment analysis, RAG, GraphRAG) over millions of records to build competitive and market intelligence tools. My Master's research with Airbus at Cranfield was real-time computer vision for autonomous aircraft refuelling, benchmarking LSTM, GRU and Transformer models on YOLOv10 detection.

<img width="100%" src="assets/footer.svg" alt="" />
