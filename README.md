<h1 align="center">Hey, I'm Sajid 👋</h1>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=EnigmaEngineer&label=Profile%20Views&color=brightgreen&style=flat-square" alt="profile views">
</p>

<p align="center">
  <b>AI Data Engineer · Pipelines and ML systems that measure whether they actually work</b>
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
| **Focus** | Systems that report their own accuracy. Measured out of sample, with the failures left in the README. |
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
| [rag-eval-harness](https://github.com/EnigmaEngineer/rag-eval-harness) | Retrieval that measures itself. Hybrid BM25 and dense search, cross-encoder reranking, recall@k and MRR against a golden set. **BM25 alone beat the hybrid on recall@5. The reranker cost 4.4s a query and came off the default path.** | Python · FAISS · sentence-transformers | Complete, 42 commits |
| [pipeline-observability](https://github.com/EnigmaEngineer/pipeline-observability) | Catching a broken pipeline before the dashboard consumers do. Freshness, volume, schema and distribution monitors. **The volume monitor's own fire rate was measured out of sample and failed its gate, so it no longer pages. Including on the fault it was built for.** | Python · DuckDB | Complete, 39 commits |
| [text-to-sql-guardrails](https://github.com/EnigmaEngineer/text-to-sql-guardrails) | Schema retrieval, static validation, EXPLAIN cost ceiling, self correction. The guardrails are the product. **A system with no guardrails at all scores 73.3% on the frozen set against this repo's 90%, so every guardrail in it is worth five questions. The guard is scored directly and no model is called.** | Python · DuckDB | Complete, 44 commits |
| [streaming-clickstream-lakehouse](https://github.com/EnigmaEngineer/streaming-clickstream-lakehouse) | Late events, watermarks, session windows, exactly once writes. The parts of streaming that actually break. **Delete the checkpoint and reprocess everything and the table is byte identical. Delete the table and keep the checkpoint and the job exits clean with zero rows. The checkpoint is a progress optimisation carrying a correctness liability.** | Kafka · Spark Structured Streaming · DuckDB | Complete, 35 commits |
| [cdc-postgres-warehouse](https://github.com/EnigmaEngineer/cdc-postgres-warehouse) | Idempotent merges under chaos testing. Kill the consumer mid batch, replay, reconcile clean. **The merge being idempotent is not the same as being able to resume. The ledger stored a batch number, and a restart that batches differently drops everything between the two resume points. 2,100 records at a restart batch of 600 against an original 250, with nothing reporting an error.** | Postgres · logical decoding · Debezium · DuckDB | Complete, 38 commits |
| [warehouse-data-contracts](https://github.com/EnigmaEngineer/warehouse-data-contracts) | A DAG that refuses to publish bad data. Contracts generate both the ingestion checks and the dbt tests. **20 single column constraints over 179,314 real rows found nothing at all. Three checks reading two columns found 572 bad rows. The rule shape was the problem and no amount of threshold tuning would have reached it.** | Airflow · dbt · DuckDB | Complete, 40 commits |
| [feature-store-realtime](https://github.com/EnigmaEngineer/feature-store-realtime) | One feature definition for training and serving, with a skew test that fails CI when they drift. **The drift monitor reports nothing while 769,489 of 1,371,923 served feature cells are wrong and 16,357 requests flip their decision. Staleness is a per row error and a distribution monitor cannot see it.** | PySpark · Redis · FastAPI | Complete, 38 commits |
| [model-cicd-registry](https://github.com/EnigmaEngineer/model-cicd-registry) | Promotion gates. A model cannot reach production unless it beats the incumbent on a holdout both are scored on. **Comparing the two numbers the runs recorded compares two different test sets. Moving only the random seed moves that number by 95 times the smallest real difference the gate can detect.** | MLflow · Python | Complete, 45 commits |
| [pii-governance-toolkit](https://github.com/EnigmaEngineer/pii-governance-toolkit) | Column classification with a confidence score, masking policies, a review queue and an access audit. The scanner never reads a value. **The compliance report it generates answers 25 of the 58 questions it asks itself. Five of five tables refuse a residual risk number, because every one holds a column the tool declined to decide on, and the k it used to publish was computed over the wrong set.** | Python · DuckDB · SQL lineage | Complete, 37 commits |
| Spark job profiler | Reads event logs and says why a job was slow. Skew, spill, wrong partition count | PySpark · pandas | Planned |

**The most recent one, from the compliance report.** A scanner is judged on what it finds. This one is more interesting for what it declines. The report it produces answers 25 of the 58 questions it asks itself and refuses 33. The refusals are records rather than blank rows. Each one carries the question, the subject, why it will not answer and what would close it. Two of them say nothing closes this, which is the honest reading of a Safe Harbor clause whose membership depends on values a metadata scan never sees. The residual risk section refuses on all five tables. It used to answer for one, the aggregated mart, at a k of 20. Then a bug that had been deleting a column's evidence before the classifier ever saw it got fixed, that column landed in the review band, and the mart became unmeasurable. The k of 20 had been computed over a quasi set missing a column in Safe Harbor scope, so a precise answer about the wrong set turned into a refusal, and the report got better.

**Before that, from the access audit.** Access reviews usually work from grants. List each role, list the tables it can select from, and sign off. The BI analyst role here holds one reporting mart and nothing else, so a review calls it well scoped. The problem is that a grant on a table doesn't bound what it exposes. The mart groups by day and department and postal code. A grouping key is a copy of the source value, not a summary of it. Following the value through the SQL that built the mart, one user is granted the patient table and six read patients' postal codes. Five of them hold no grant on the table the column lives in. Two columns from that same table have identical grants. One is reachable by six people and the other by one, and the difference isn't anywhere in the patient table. The same report can't say whether anybody read the SSN column either. A `SELECT *` logs a table and no column, so for 16 of 25 flagged columns the honest answer is between nobody and one person.

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
- **A restart lost 2,100 records silently** because the resume point was a batch number rather than an offset. Undershoot the original batch size and idempotency covers it. Overshoot and the loss is exactly the size difference times the batches already applied
- **Splitting a Debezium connector per table cost 3.98x the transaction framing** to deliver the identical 880 row changes, because BEGIN and COMMIT are transaction scoped and a publication does not filter them
- **20 single column data quality rules over 179,314 real rows caught nothing.** Three rules reading two columns caught 572. 493 requests closed with no closing date and 12 closed before they were created. The rule shape was the problem, so tuning the thresholds would never have found it
- **A drift monitor sat green while more than half the served feature vectors were wrong.** 769,489 of 1,371,923 cells, and 16,357 requests flipping their decision, against a drift index that never got above 0.0034. Staleness is a per row error and a distribution monitor is blind to it by construction
- **A promotion gate was comparing two models on two different test sets.** Moving only the random seed moved the recorded metric by 95 times the smallest real difference the gate could detect
- **A grant review said one user could see patient postal codes and six had read them.** Five did it through a reporting mart they were legitimately granted, because a `GROUP BY` key is a copy of the source column. Two columns in the same table with identical grants came out reachable by six people and by one
- **Making a classifier see one more column turned its only confident risk number into a refusal.** The mart reported k of 20, measured over a column set that was missing an admission date in HIPAA scope. Once the classifier stopped discarding that column's evidence, the table correctly refused to report anything until a person reviews it
- **Every number above is reproducible.** Each repo ships the command that produced it, and one repo re-runs those commands and grades its own README against them

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
