# Augusto Oliveira

**AI Engineer — production RAG systems.** · Natal, Brazil (UTC−3)

[![Email](https://img.shields.io/badge/Email-5980A6?style=for-the-badge&logo=maildotru&logoColor=white)](mailto:gutonetodev@proton.me)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-5980A6?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/augusto-oliveira-4a8068235/)
[![Portfolio](https://img.shields.io/badge/Portfolio-5980A6?style=for-the-badge&logo=googlechrome&logoColor=white)](https://augusto240.github.io/Personal-Site/)
[![ORCID](https://img.shields.io/badge/ORCID-5980A6?style=for-the-badge&logo=orcid&logoColor=white)](https://orcid.org/0009-0003-7020-6469)

> ### Open to full-time remote work as an AI or backend engineer.
> Currently finishing my degree in Internet Systems at IFRN (expected 2027).


---

I build and operate retrieval-based AI systems that have to work in front of real users.

For the last year and a half I was the primary engineer on **SmartFAQ**, a Retrieval-Augmented Generation assistant for Brazil's Ministry of Communications, built at CCSL/IFRN. Most of my work sat in the part of RAG that doesn't demo well and decides whether the thing survives contact with production: evaluation, tracing, guardrails, failure modes, and latency.

## What I actually worked on

### SmartFAQ — RAG assistant for a federal ministry

`Private repository (client-owned)` · Python · LangChain · Milvus · Flask · Celery · Redis · PostgreSQL · Ollama

The code belongs to the client and lives in a private GitLab repo, so here is what I built rather than a link.

<details>
<summary><b>The seven things I actually shipped</b></summary>

<br>

- **Retrieval pipeline** — BGE-M3 embeddings into Milvus, cosine search, context assembly, generation with Llama 3.3 70B via Ollama, orchestrated across four services.
- **Evaluation harness** — context precision and context recall, an LLM-as-a-judge, and calibration tests that measure how much the judge itself moves the scores. This is the part I'd most want to talk about in an interview.
- **Observability** — a single request ID propagated across API, queue, AI service and vector store; ten structured trace events with per-phase timing; a provenance field on every response that says whether the answer came from real vector retrieval, a fallback, or an error.
- **Fail-closed safety** — I audited the codebase and found five undocumented paths that could return an answer without ever querying the vector index. Removed them and made the pipeline return HTTP 503 instead of quietly fabricating text, with automated conformance tests to keep it that way.
- **Reliability** — traced a full outage to a synchronous guardrail warm-up blocking the API from binding its port; moved it to a background thread with a keyword fallback. Added drift detection between the relational database and the vector index, and a filesystem lock to stop concurrent writers corrupting it.
- **Performance** — profiled the system and documented the ten biggest latency bottlenecks with file-and-line evidence, showing LLM inference at 50–80% of total request time and serialised URL validation as the second largest cost.
- **Ingestion** — Selenium crawlers for JavaScript-rendered government portals (accordion content, cross-domain documents, SSL and popup blockers), feeding an ETL that produced the structured Q&A knowledge base.

</details>

### Also built

| Project | One line | Stack |
| :--- | :--- | :--- |
| **Vehicle Access Control System** | End-to-end access management platform — web front end, REST API, real-time messaging with cameras and access hardware, institutional SSO, automated backups with restore testing. | Angular · TypeScript · Node.js · Express · MySQL · Docker · MQTT |
| **Municipal Data Scraper** | Scraping pipeline for public-sector portals with JavaScript-rendered content and unstable page behaviour. | Python · Selenium · PostgreSQL |
| **Jiu-Jitsu Academy Manager** | Small full-stack platform for managing students, classes and operational data at a martial arts academy. Built because I train there. | Ruby · Sinatra · PostgreSQL · Docker |

---

## Tech

| | |
| :--- | :--- |
| **AI / LLM** | ![Python](https://img.shields.io/badge/Python-5980A6?style=for-the-badge&logo=python&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-5980A6?style=for-the-badge&logo=langchain&logoColor=white) ![Milvus](https://img.shields.io/badge/Milvus-5980A6?style=for-the-badge&logo=milvus&logoColor=white) ![Ollama](https://img.shields.io/badge/Ollama-5980A6?style=for-the-badge&logo=ollama&logoColor=white) ![BGE-M3](https://img.shields.io/badge/BGE--M3-5980A6?style=for-the-badge&logo=huggingface&logoColor=white) <br> RAG architecture · retrieval evaluation · guardrails · prompt engineering |
| **Backend** | ![Flask](https://img.shields.io/badge/Flask-5980A6?style=for-the-badge&logo=flask&logoColor=white) ![Django](https://img.shields.io/badge/Django-5980A6?style=for-the-badge&logo=django&logoColor=white) ![Celery](https://img.shields.io/badge/Celery-5980A6?style=for-the-badge&logo=celery&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-5980A6?style=for-the-badge&logo=redis&logoColor=white) ![Node.js](https://img.shields.io/badge/Node.js-5980A6?style=for-the-badge&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/Express-5980A6?style=for-the-badge&logo=express&logoColor=white) |
| **Data** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-5980A6?style=for-the-badge&logo=postgresql&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-5980A6?style=for-the-badge&logo=mysql&logoColor=white) ![Selenium](https://img.shields.io/badge/Selenium-5980A6?style=for-the-badge&logo=selenium&logoColor=white) ![pandas](https://img.shields.io/badge/pandas-5980A6?style=for-the-badge&logo=pandas&logoColor=white) ![Airflow](https://img.shields.io/badge/Airflow-5980A6?style=for-the-badge&logo=apacheairflow&logoColor=white) ![MLflow](https://img.shields.io/badge/MLflow-5980A6?style=for-the-badge&logo=mlflow&logoColor=white) |
| **Infra** | ![Docker](https://img.shields.io/badge/Docker-5980A6?style=for-the-badge&logo=docker&logoColor=white) ![Git](https://img.shields.io/badge/Git-5980A6?style=for-the-badge&logo=git&logoColor=white) ![GitLab CI](https://img.shields.io/badge/GitLab%20CI-5980A6?style=for-the-badge&logo=gitlab&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-5980A6?style=for-the-badge&logo=linux&logoColor=white) |
| **Frontend** | ![TypeScript](https://img.shields.io/badge/TypeScript-5980A6?style=for-the-badge&logo=typescript&logoColor=white) ![Angular](https://img.shields.io/badge/Angular-5980A6?style=for-the-badge&logo=angular&logoColor=white) ![React](https://img.shields.io/badge/React-5980A6?style=for-the-badge&logo=react&logoColor=white) |

---

<sub>Full project write-ups at [augusto240.github.io/Personal-Site](https://augusto240.github.io/Personal-Site/)</sub>
