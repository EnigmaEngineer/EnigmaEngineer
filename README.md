<h1 align="center">Hey, I'm Sajid 👋</h1>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=EnigmaEngineer&label=Profile%20Views&color=brightgreen&style=flat-square" alt="profile views">
</p>

<p align="center">
  <b>AI Data Engineer · Turning messy data into production ML and LLM systems · Retrieval Systems that report their own accuracy</b>
</p>

<p align="center">
  <a href="mailto:syedsajidhussain1999@gmail.com"><img src="https://img.shields.io/badge/email-syedsajidhussain1999%40gmail.com-2b2b2b?style=flat-square&labelColor=4a4a4a" alt="email"></a>
  <a href="https://www.linkedin.com/in/thesyedsajid"><img src="https://img.shields.io/badge/linkedin-thesyedsajid-2b2b2b?style=flat-square&labelColor=4a4a4a" alt="linkedin"></a>
</p>

---

Three years building data pipelines in compliance driven environments. Spark, Kafka,
Snowflake and Airflow. Now applying the same instinct to AI systems, where the interesting
question is not whether it produces an answer but whether you can prove the answer is right.

A few things I've shipped:

Dropped pipeline failures 70%+ with Great Expectations validation, dead letter queues and self healing Airflow DAGs.

Built production RAG on LangChain and FAISS. Hybrid BM25 and semantic search with cross encoder re ranking, which lifted retrieval accuracy 20%+.

Served models from FastAPI on Kubernetes at ~500 req/s and sub 150ms p95. Drift detection on KS and CUSUM and PSI caught real shifts inside 24 hours.

I am currently building ten projects in public. Every repo ships with measured numbers and an honest limitations section. Where something did not work, the README says so.

<details open>
<summary><b>Currently</b></summary>
<br>

| | |
|---|---|
| **Building** | Ten data engineering and AI projects in public. Streaming, CDC, orchestration, retrieval, MLOps. Committed publicly as it is built. |
| **Focus** | Retrieval systems with real evaluation. Recall@k and MRR on a golden set, not vibes. |
| **Background** | Data Engineer and AI Developer. Spark and Kafka pipelines at 50GB/day, Snowflake tuning, production RAG. |
| **Education** | M.S. Information Systems, Cleveland State University |

</details>

<details open>
<summary><b>Stack</b></summary>
<br>

```
Languages    Python · SQL · Scala · Java · R
Processing   Apache Spark · Structured Streaming · PySpark · pandas
Streaming    Apache Kafka · Debezium · exactly once sinks
Warehouse    Snowflake · DuckDB · dbt · dimensional modelling
Orchestrate  Apache Airflow · Great Expectations · data contracts
AI / ML      LangChain · FAISS · sentence-transformers · scikit-learn
Serving      FastAPI · Docker · MLflow
Cloud        AWS · Azure · GCP
```

</details>

<details open>
<summary><b>Building in public</b></summary>
<br>

Ten projects. Every one maps to something I have actually done in production, so the repo
is evidence rather than a tutorial I followed. Numbers below are measured on my own machine
and reproduced in the repo.

| Project | What it proves | Stack | Status |
|---|---|---|---|
| [rag-eval-harness](https://github.com/EnigmaEngineer/rag-eval-harness) | Retrieval that measures itself. Hybrid BM25 and dense search, cross-encoder reranking, recall@k and MRR against a golden set. **BM25 alone beat the hybrid on recall@5. The reranker cost 4.4s a query and came off the default path.** | Python · FAISS · sentence-transformers | Complete, 37 commits |
| [pipeline-observability](https://github.com/EnigmaEngineer/pipeline-observability) | Catching a broken pipeline before the dashboard consumers do. Freshness, volume, schema and distribution monitors. **The volume monitor's own fire rate was measured out of sample and failed its gate, so it no longer pages. Including on the fault it was built for.** | Python · DuckDB | Complete, 36 commits |
| [text-to-sql-guardrails](https://github.com/EnigmaEngineer/text-to-sql-guardrails) | Schema retrieval, static validation, EXPLAIN cost ceiling, self correction. The guardrails are the product. **A system with no guardrails at all scores 73.3% on the frozen set against this repo's 90%, so every guardrail in it is worth five questions. The guard is scored directly and no model is called.** | Python · DuckDB | Complete, 42 commits |
| [streaming-clickstream-lakehouse](https://github.com/EnigmaEngineer/streaming-clickstream-lakehouse) | Late events, watermarks, session windows, exactly once writes. The parts of streaming that actually break. **Delete the checkpoint and reprocess everything and the table is byte identical. Delete the table and keep the checkpoint and the job exits clean with zero rows. The checkpoint is a progress optimisation carrying a correctness liability.** | Kafka · Spark Structured Streaming · Snowflake | Complete, 33 commits |
| Change data capture to warehouse | Idempotent merges under chaos testing. Kill the consumer mid batch, replay, reconcile clean | Postgres · Debezium · Kafka | Planned |
| Warehouse with data contracts | A DAG that refuses to publish bad data. Contracts generate both the ingestion checks and the dbt tests | Airflow · dbt · Snowflake | Planned |
| Feature store and inference | One feature definition for training and serving, with a skew test that fails CI when they drift | PySpark · Redis · FastAPI | Planned |
| Model CI/CD | Promotion gates. A model cannot reach production unless it beats the incumbent on a frozen holdout | MLflow · GitHub Actions | Planned |
| PII discovery and governance | Column classification with confidence scoring, masking policies and an access audit an auditor would accept | Snowflake · Python · spaCy | Planned |
| Spark job profiler | Reads event logs and says why a job was slow. Skew, spill, wrong partition count | PySpark · pandas | Planned |

**What the eval harness actually found.** 3,212 chunks across 241 docs. BM25 scored recall@5 0.700 and MRR@10 0.607 at 1ms a query. Dense scored 0.600 and 0.483 at 23ms. The cross encoder reranker took 4,412ms and did not improve the question it was built to fix, so it is off by default. Fusion stayed as a stated design preference, not a measured win. Seven of eight quality comparisons move three questions or fewer and none could reach significance at any effect size on a set this small. That is in the README too.

</details>

<details open>
<summary><b>Experience</b></summary>
<br>

**Data and ML Intern** · Rediantt LLC · 2025

- Rewrote Python parsers and added Great Expectations validation, cutting pipeline errors by over 70%
- Containerized pipelines on AWS, 25% lower processing latency
- Enforced idempotency in PySpark and SQL merge logic so reruns stop duplicating rows

**Data Engineer and AI Developer** · Infoville Solutions · 2020 to 2023

- Spark, Airflow and dbt pipelines processing up to 50GB daily
- Kafka and PySpark sessionization, cutting query latency from 300ms to under 50ms
- Snowflake clustering and query rewrites, taking reports from 15 minutes to 90 seconds
- LangChain and FAISS hybrid semantic search in production, 22% better retrieval relevance
- FastAPI model serving under 150ms inference latency
- MLOps and CI/CD workflows, 40% fewer deployment failures

</details>

<details open>
<summary><b>Notable wins</b></summary>
<br>

From production work on compliance driven data platforms.

- **300ms to under 50ms query latency.** Kafka and PySpark sessionization with feature extraction on a real time stream
- **15 minutes to 90 seconds report execution.** Redefined Snowflake clustering keys and rewrote the underlying SQL
- **70% fewer pipeline errors.** Rewrote failing Airflow DAG parsers and added Great Expectations validation at ingestion
- **40% fewer deployment failures.** MLOps and CI/CD workflows with automated testing and staged rollout
- **22% better retrieval relevance.** LangChain and FAISS hybrid semantic search in a production RAG pipeline
- **Sub 150ms inference latency.** FastAPI model serving, containerized, under real traffic
- **50GB processed daily.** Spark, Airflow and dbt pipelines, led as a team
- **15% better prediction accuracy.** Demand forecasting and anomaly detection on high volume transactional data
- **25% lower processing latency.** Containerized Python pipelines on AWS

From the current build in public program, measured on my own machine.

- **BM25 at 1ms beat dense retrieval at 23ms** on recall@5 over 3,212 Spark doc chunks. The simplest method won
- **Cross encoder reranking cost 4,412ms a query** for no gain on the question it was built to fix, so it came off the default path
- **Every number above is reproducible.** Each repo ships the command that produced it

</details>

<details>
<summary><b>Earlier projects</b></summary>
<br>

| Project | What it does | Stack |
|---|---|---|
| [Production RAG Enterprise Document Assistant](https://github.com/EnigmaEngineer/Production-RAG-Enterprise-Document-Assistant) | Hybrid retrieval with cross encoder reranking, citations, vLLM serving, Kubernetes deployment, evaluation framework and CI/CD | Python · FAISS · FastAPI · Kubernetes |
| [Real Time AI Chatbot with Guardrails and Monitoring](https://github.com/EnigmaEngineer/Real-Time-AI-Chatbot-with-Guardrails-and-Monitoring) | Support agent with RAG, safety guardrails, drift detection, Prometheus and Grafana monitoring, A/B testing | Python · RAG · Prometheus · Grafana |
| [localrag](https://github.com/EnigmaEngineer/localrag) | Local first RAG pipeline with Ollama and OpenAI support | Python · Ollama |
| [rolecolor ai](https://github.com/EnigmaEngineer/rolecolor-ai) | Resume analyzer using NLP | Python · NLP |

</details>

<details>
<summary><b>Publications and certifications</b></summary>
<br>

**Publication**
High Tension Line Surveillance Robot · International Journal of Applied Engineering Research
[Paper](https://www.ripublication.com/ijaer20/ijaerv15n5_13.pdf)

**Certifications**
AWS Certified AI Practitioner · IBM Python for Data Science and AI · IBM Generative AI (Introduction, Prompt Engineering) · IBM AI Essentials · BCG GenAI Job Simulation · Goldman Sachs Risk Job Simulation

</details>

---

<p align="center">
  Working on streaming pipelines or retrieval evaluation? Happy to talk.
</p>
