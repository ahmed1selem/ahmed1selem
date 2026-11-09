# Ahmed Saleem

### AI Engineer · LLM agents · hybrid RAG · real-time voice · Arabic & English

I build complete LLM applications: the agents and retrieval, the model-access layer, the guardrails, the
tests and deployment, and the interface people actually use. Most of what I build works in both Arabic and
English.

🎓 M.Sc. in Computer & Automatic Control Engineering, Tanta University (in progress; thesis on monitoring ML
models under data drift) · ITI AI & Machine Learning track, 1,431 hours (2025–2026) ·
B.Sc. Computer & Automatic Control Engineering, Tanta University (2024)

---

## Featured systems

### 🎙️ Lisan AI · multi-tenant voice & chat customer-service agent
*Code is private · live demo on request*

An agent that answers a company's customers by chat or by phone in Egyptian Arabic, looks up their orders,
drafts actions for the customer to confirm, and hands the call to a human agent with the case already written.

- **Architecture:** FastAPI · LangGraph orchestrator (question / action / escalation agents) · one model
  adapter layer with model roles · hybrid retrieval (BGE-M3 + BM25, rank fusion, confidence gate) on Qdrant ·
  per-tenant MCP tool servers · PostgreSQL · React agent console · Docker Compose on AWS EC2
- **Voice:** Gemini Live speech-to-speech over Twilio phone calls and browser WebRTC, SIP escalation to a human
- **Multi-tenant:** a new brand is a config file and a knowledge base, generated in Arabic and English from the
  brand's SOP documents
- **Under load:** seat-based admission control; the next caller goes to a human, not a degraded bot

### 📰 [Briefley](https://github.com/ahmed1selem/brifley/tree/feature/pipeline-refactor) · Arabic & English news intelligence platform
Collects news from 20+ outlets and Telegram channels, summarises it in Arabic or English, groups each story
across sources, and answers questions with citations.

- **Pipeline:** asyncio queues and workers (RSS, trafilatura/Playwright scraping, classification,
  summarisation) plus a live Telegram listener · embedding-based deduplication · two-stage clustering per category
- **Models:** PEGASUS (EN) and AraBART (AR) summarisation · Sentence-Transformers · Qdrant
- **Agentic RAG:** local Llama-3.2 with native tool calls over vector search, story clusters and Wikipedia;
  no per-question API cost
- **App:** FastAPI backend and web UI where users manage their own sources

### 💬 [Sanad](https://github.com/ahmed1selem/Mental-Health-RAG-Chatbot) · mental-health support chatbot
An empathetic support chatbot that reads the user's emotional state first, answers from vetted material
with citations, and handles a crisis differently from an ordinary question, by text or voice.

- **Retrieval & prompts:** hybrid BM25 + Qdrant with reranking · DSPy/GEPA-compiled prompts · 0.95+
  faithfulness and 0.89+ context recall (RAGAS / DeepEval)
- **Models:** XLM-RoBERTa + LoRA emotion classifier (92.7% test accuracy) served via ONNX on CPU · Whisper voice input
- **Operations:** Docker · GitHub Actions deploy to AWS EC2 with deploy-time secrets · OpenTelemetry with no
  user text in traces · Locust load tests · fallback vector store

### 📝 [Dawwen](https://github.com/ahmed1selem/Dawwen) · conversational notes agent (EN/AR)
The model proposes, code decides: edits and deletes run only after an explicit yes. One Groq client with key
rotation and failover, hybrid search inside one SQLite file, a right-to-left Arabic interface, and ~140
adversarial tests.

---

## More projects

| Project | What it is |
| --- | --- |
| **[Scoutly](https://github.com/ahmed1selem/scoutly-ai)** | Multi-agent football scouting platform: a planner plus four specialist agents, FBref data served through an MCP server, RAG, human-in-the-loop review, LangSmith tracing. |
| **[Pinpoint](https://github.com/ahmed1selem/pinpoint)** | Vision-only GUI grounding for Windows: give it a screenshot and a sentence, it returns the pixel to click. Implements ReGround from ScreenSpot-Pro. |
| **[NileTel Support Assistant](https://github.com/ahmed1selem/NileTel-Support-Assistant)** | Telecom support RAG (FAISS + BM25) that opens tickets through an n8n workflow. |
| **[Hand Gesture Classification](https://github.com/ahmed1selem/ML1_project)** | Real-time 18-class gesture recognizer: XGBoost on MediaPipe landmarks with 30 engineered features, 98.66% accuracy. |
| **[Bitcoin Forecasting Portal](https://github.com/ahmed1selem/bitcoin-forecasting-portal)** | ARIMA, Prophet and XGBoost compared, with quantile-regression confidence bands. |

---

## Tools

**LLM & agents:** LangGraph · MCP · tool calling · hybrid RAG · DSPy · RAGAS / DeepEval · Groq · Gemini · Ollama
**ML:** PyTorch · Hugging Face · LoRA / PEFT · ONNX Runtime · scikit-learn · XGBoost
**Shipping:** FastAPI · React · WebRTC / Twilio · PostgreSQL · Qdrant · Docker · GitHub Actions · AWS EC2 · OpenTelemetry · pytest

📫 [LinkedIn](https://www.linkedin.com/in/ahmed-saleem-/) · ahmedashsaleem@gmail.com
