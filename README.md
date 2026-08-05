<h1 align="center">Syed Sajid Hussain</h1>

<p align="center">
  <b>AI Data Engineer</b> · Streaming and batch pipelines · Retrieval systems that report their own accuracy
</p>

<p align="center">
  <a href="mailto:syedsajidhussain1999@gmail.com"><img src="https://img.shields.io/badge/email-syedsajidhussain1999%40gmail.com-informational?style=flat-square" alt="email"></a>
  <a href="https://www.linkedin.com/in/thesyedsajid"><img src="https://img.shields.io/badge/linkedin-connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="linkedin"></a>
  <a href="https://github.com/EnigmaEngineer"><img src="https://img.shields.io/badge/github-EnigmaEngineer-181717?style=flat-square&logo=github&logoColor=white" alt="github"></a>
</p>

---

Three years building data pipelines in compliance-driven environments. Spark, Kafka,
Snowflake, Airflow. Now applying the same instinct to AI systems, where the interesting
question is not whether it produces an answer but whether you can prove the answer is right.

I am currently building ten projects in public, one day at a time. Every repo ships with
measured numbers and an honest limitations section. Where something did not work, the
README says so.

---

<details open>
<summary><h3>Currently</h3></summary>

| | |
|---|---|
| **Building** | Ten data engineering and AI projects in public. Streaming, CDC, orchestration, retrieval, MLOps. One day of work per day, committed publicly. |
| **Focus** | Retrieval systems with real evaluation. Recall@k and MRR on a golden set, not vibes. |
| **Background** | Data Engineer and AI Developer. Spark and Kafka pipelines at 50GB/day, Snowflake tuning, production RAG. |
| **Education** | M.S. Information Systems, Cleveland State University |

</details>

<details open>
<summary><h3>Stack</h3></summary>

```
Languages    Python · SQL · Scala · Java · R
Processing   Apache Spark · Structured Streaming · PySpark · pandas
Streaming    Apache Kafka · Debezium · exactly-once sinks
Warehouse    Snowflake · DuckDB · dbt · dimensional modelling
Orchestrate  Apache Airflow · Great Expectations · data contracts
AI / ML      LangChain · FAISS · sentence-transformers · scikit-learn
Serving      FastAPI · Docker · MLflow
Cloud        AWS · Azure · GCP
```

</details>

<details open>
<summary><h3>Building in public</h3></summary>

Ten projects, seven days each. Every one maps to something I have actually done in
production, so the repo is evidence rather than a tutorial I followed.

| Project | What it proves | Stack | Status |
|---|---|---|---|
| [rag-eval-harness](https://github.com/EnigmaEngineer/rag-eval-harness) | Retrieval that measures itself. Hybrid BM25 and dense search, cross-encoder reranking, recall@k and MRR against a golden set, CI gate on regression | Python · FAISS · sentence-transformers | In progress |
| [streaming-clickstream-lakehouse](https://github.com/EnigmaEngineer/streaming-clickstream-lakehouse) | Late events, watermarks, session windows, exactly-once writes. The parts of streaming that actually break | Kafka · Spark Structured Streaming · Snowflake | Day 1 done, parked |
| Pipeline observability | Freshness, volume and distribution monitors with seasonal baselines. Catching a broken pipeline before the dashboard does | Airflow · Great Expectations · Snowflake | Planned |
| Text-to-SQL with guardrails | Schema retrieval, static validation, EXPLAIN cost ceiling, self-correction. The guardrails are the product | LangChain · FAISS · Snowflake | Planned |
| Change data capture to warehouse | Idempotent merges under chaos testing. Kill the consumer mid-batch, replay, reconcile clean | Postgres · Debezium · Kafka | Planned |
| Warehouse with data contracts | A DAG that refuses to publish bad data. Contracts generate both the ingestion checks and the dbt tests | Airflow · dbt · Snowflake | Planned |
| Feature store and inference | Same feature definition for training and serving, with a skew test that fails CI when they drift | PySpark · Redis · FastAPI | Planned |
| Model CI/CD | Promotion gates. A model cannot reach production unless it beats the incumbent on a frozen holdout | MLflow · GitHub Actions | Planned |
| PII discovery and governance | Column classification with confidence scoring, masking policies, and an access audit an auditor would accept | Snowflake · Python · spaCy | Planned |
| Spark job profiler | Reads event logs and says why a job was slow. Skew, spill, wrong partition count | PySpark · pandas | Planned |

</details>

<details open>
<summary><h3>Experience</h3></summary>

**Data Engineer and AI Developer** · Infoville Solutions · 2020 to 2023

- Spark, Airflow and dbt pipelines processing up to 50GB daily
- Kafka and PySpark sessionization, cutting query latency from 300ms to under 50ms
- Snowflake clustering and query rewrites, taking reports from 15 minutes to 90 seconds
- LangChain and FAISS hybrid semantic search in production, 22% better retrieval relevance
- FastAPI model serving under 150ms inference latency
- MLOps and CI/CD workflows, 40% fewer deployment failures

**Data and ML Intern** · Rediantt LLC · 2025

- Rewrote Python parsers and added Great Expectations validation, cutting pipeline errors by over 70%
- Containerized pipelines on AWS, 25% lower processing latency
- Enforced idempotency in PySpark and SQL merge logic so reruns stop duplicating rows

</details>

<details>
<summary><h3>Publications and certifications</h3></summary>

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
