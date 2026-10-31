<h1 align="center">Sanskrati Patel</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&duration=2600&pause=700&color=00F7FF&center=true&vCenter=true&width=860&lines=%3E+tokenize(%22Sanskrati+Patel%22);%3E+embed()+%E2%86%92+%5BBackend+%E2%8A%95+Agentic+AI%5D;%3E+retrieve(top_k%3D3)+%E2%86%92+FastAPI+%E2%80%A2+LangGraph+%E2%80%A2+RAG;%3E+generate()+%E2%86%92+production+systems+with+guardrails+%26+evals" alt="typing banner"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/arch-Backend_%2B_Agentic_AI-7C3AED?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/experience-2%2B_yrs_prod_%2B_6mo_freelance-0EA5E9?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/status-open_to_work-22C55E?style=for-the-badge"/>
</p>

---

### 🧬 `model_card.yaml`

```yaml
model_id:        sanskratipatel/backend-ai-engineer
architecture:    Python backend  ⊕  agentic AI (LangGraph · RAG · tool calling)
pretraining:     FastAPI · Django REST · PostgreSQL · MongoDB · Redis · RabbitMQ · Socket.IO
fine_tuned_on:   LangGraph agents · RAG pipelines · guardrails · LLM evaluation · multi-provider fallback
serving:         production — order, inventory and procurement platforms used daily across 12 sites
context_window:  Bhopal, India  →  open to relocation
eval_metrics:
  order_turnaround:  7 days → 1 day
  daily_volume:      1,400+ orders/day · 200+ staff
  api_latency:       9 s → 1.3 s  ·  8.7 s → 0.34 s
intended_use:    Backend Engineer · AI / GenAI Engineer roles
```

---

### 🧠 `forward_pass()` — how I build an AI system

```text
 user message ─▶ [ tokenize ] ─▶ [ embed ] ─▶ [ vector search: top_k ] ─▶ [ rerank ] ─┐
                                                                                      ▼
 reply ◀─ [ output guardrail ] ◀─ [ LLM + tool calls ] ◀─ [ intent router ] ◀─ [ input guardrail ]
            own-data-only            LangGraph, max steps      small model         injection checks
                                     fallback across providers
 every step ─▶ logs · traces · eval set (run before every prompt or model change)
```

---

### ⚡ Attention heads — what I focus on

| Head | What it attends to | Evidence |
|---|---|---|
| 🏭 **Backend at scale** | data consistency, query performance, integrations | paper warehouse → digital workflow: **7 days → 1 day** across **12 sites**; FastAPI backend for **200+ staff / 1,400+ orders a day** |
| ⚡ **Performance** | N+1 queries, composite indexes, caching | slow APIs **9 s → 1.3 s** and **8.7 s → 0.34 s** (`EXPLAIN ANALYZE`, selective Redis caching) |
| 🔒 **Correctness** | race conditions, idempotency, atomic updates | fixed a production race that could allocate the same stock twice |
| 🤖 **Agentic AI** | LangGraph, tool calling, RAG, guardrails, evals | production WhatsApp agent for farmers (team of three) + a warehouse chatbot |
| 📨 **Async & real time** | queues, workers, live updates | invoicing on RabbitMQ workers; live updates over Socket.IO |

---

### 🤖 `class AgenticAIWork`

```python
class WhatsAppFarmerAgent(LangGraphAgent):          # production · team of three
    llm        = "Llama 3.3 70B on Groq"
    tools      = ["order_status", "shipment_tracking", "product_rag", "faq_rag"]   # allow-listed
    retrieval  = RAG(chunking="recursive", embeddings="multilingual", store="Chroma", reindex="background job")
    safety     = ["only the farmer's own data", "prompt-injection checks", "human handoff on 'Talk to Agent'"]
    reliability= "fallback to another provider on rate limit or free-credit quota"
    quality    = "eval set of ~50 real questions + injection attempts, run before every change"
    cost       = ["no LLM for menu taps", "small model for intent", "local embeddings", "capped tokens", "Redis cache"]


class WarehouseChatbot(Chatbot):                     # built end to end
    llm   = "Llama 3.1 8B"            # extracts the intent only
    flow  = "intent → role-permission check → database lookup → template reply"   # numbers never invented
```

---

### 🗂️ `vector_db.query("featured projects", top_k=2)`

<table>
<tr>
<td width="50%" valign="top">

#### 🌾 [FarmHelp Agent](https://github.com/sanskratipatel/FarmHelp-Agent)
`score: 0.99 · status: in active development`

WhatsApp-style support agent for farmers (English, Hindi, Hinglish), every decision measured and documented.

- RAG: field-group + header/recursive chunking, multilingual embeddings, Chroma, hash-based sync
- Retrieval eval by language → found a Hinglish gap → query rewriting
- Tools with the customer's phone injected from LangGraph state
- LLM chain on Groq: Redis cooldowns, circuit breaker, LangSmith tracing
- Guardrails: intent router, off-topic → "I don't know", inappropriate → "No"

📐 [System design & decisions](https://github.com/sanskratipatel/FarmHelp-Agent/blob/main/docs/SYSTEM_DESIGN.md)

`LangGraph` `Groq` `Chroma` `MongoDB` `Redis` `LangSmith`

</td>
<td width="50%" valign="top">

#### ⏱️ [Job Scheduler](https://github.com/sanskratipatel/Job-Sheduler)
`score: 0.97 · status: deployed on AWS EC2`

Platform to create, schedule, pause, resume and monitor background jobs.

- Safe concurrent workers: `SELECT … FOR UPDATE SKIP LOCKED`
- Retries with exponential backoff
- Leases plus a reaper for crash recovery
- Docker Compose: API, workers, database, frontend

`FastAPI` `PostgreSQL` `React` `Docker` `AWS EC2`

</td>
</tr>
</table>

---

### 🧩 `embeddings` — tech stack

| Dimension | Values |
|---|---|
| **Languages** | ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-336791?logo=postgresql&logoColor=white) |
| **Backend** | ![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white) ![Django](https://img.shields.io/badge/Django_REST-092E20?logo=django&logoColor=white) ![Pydantic](https://img.shields.io/badge/Pydantic-E92063?logo=pydantic&logoColor=white) |
| **Agentic AI** | ![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?logo=langchain&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?logo=langchain&logoColor=white) ![RAG](https://img.shields.io/badge/RAG-FF6F00) ![Tool calling](https://img.shields.io/badge/Tool_calling-6D28D9) ![Evals](https://img.shields.io/badge/LLM_evals-DB2777) ![LangSmith](https://img.shields.io/badge/LangSmith-1C3C3C?logo=langchain&logoColor=white) |
| **LLMs** | ![Llama](https://img.shields.io/badge/Llama_3.x-0467DF?logo=meta&logoColor=white) ![Groq](https://img.shields.io/badge/Groq-F55036) ![GPT-4o-mini](https://img.shields.io/badge/GPT--4o--mini-412991?logo=openai&logoColor=white) |
| **Vector DBs** | ![Chroma](https://img.shields.io/badge/Chroma-FF6446) ![pgvector](https://img.shields.io/badge/pgvector-4169E1?logo=postgresql&logoColor=white) |
| **Databases** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-47A248?logo=mongodb&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white) |
| **Messaging & real time** | ![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white) ![Socket.IO](https://img.shields.io/badge/Socket.IO-010101?logo=socketdotio&logoColor=white) ![WhatsApp](https://img.shields.io/badge/WhatsApp_Business_API-25D366?logo=whatsapp&logoColor=white) |
| **Cloud & DevOps** | ![AWS](https://img.shields.io/badge/AWS_Lambda_%7C_S3-232F3E?logo=amazonwebservices&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-FCC624?logo=linux&logoColor=black) ![Render](https://img.shields.io/badge/Render-000000?logo=render&logoColor=white) |
| **Auth & integrations** | ![JWT](https://img.shields.io/badge/JWT_%2B_RBAC-000000?logo=jsonwebtokens&logoColor=white) ![Zoho](https://img.shields.io/badge/Zoho_Books_%7C_CRM-E42527?logo=zoho&logoColor=white) ![Shiprocket](https://img.shields.io/badge/Shiprocket_%7C_Delhivery-6C2BD9) |

---

### 📜 `training_history`

```text
2024-10 → now   Backend Software Engineer · Katyayani Organics · Bhopal
                order / inventory / returns / procurement platforms · Zoho, Shiprocket, Delhivery integrations
                RabbitMQ workers · Socket.IO · JWT + bitmask RBAC in Redis · scheduled AWS Lambda
                AI: production WhatsApp farmer agent (team of three) · warehouse chatbot (end to end)

2024-05 → 06    Web Development Intern · VeriTech Software IT Services
                web pages and REST API integration in agile sprints

2020 → 2024     B.Tech, Information Technology · RGPV Bhopal · CGPA 7.81
```

### 🏆 `benchmarks`

- 🧠 Ksolves AI Hackathon 2026 — participant
- 💻 200+ DSA problems on GeeksforGeeks
- ⭐ HackerRank 4★ in Python and SQL

---

### 📊 `training_curves`

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=sanskratipatel&show_icons=true&theme=tokyonight&hide_border=true" height="165" alt="GitHub stats"/>
  <img src="https://streak-stats.demolab.com/?user=sanskratipatel&theme=tokyonight&hide_border=true" height="165" alt="GitHub streak"/>
</p>
<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=sanskratipatel&theme=tokyo-night&hide_border=true" alt="Activity graph"/>
</p>

---

### 📡 `connect()`

<p align="center">
  <a href="mailto:patelsanskrati12@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
  <a href="https://www.linkedin.com/in/sanskrati-patel-b2464b223/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
  <a href="https://sanskrati-portfolio.onrender.com/"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=render&logoColor=white"/></a>
</p>

<p align="center"><code>while True: build(reliable_backends + useful_ai)</code> 🚀</p>
