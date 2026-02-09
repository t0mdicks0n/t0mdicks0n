## Tom Dickson

CTO & technical co-founder with a background in data engineering and a focus on AI.

Currently CTO at [Tendavo](https://tendavo.se), solo-building an AI platform that helps
SMBs win public procurements. Previously co-founded Panprices/Loupe (2019-2025) -- built
data infrastructure that processed millions of product offers across 15+ European markets
($1.2M raised, $1M+ first-year GMV), then pivoted to an AI-powered shelf analytics
platform trusted by Fortune 1000 brands including MillerKnoll, HAY, and Muuto.

Prior to that: founding team at [Kivra](https://kivra.com) (2013-2019), where I led
growth, data science, and product -- scaling from early stage to 100+ employees.

---

### Building now: AI-powered procurement intelligence

Solo-building a large-scale AI application from scratch at Tendavo. The platform
automates analysis of complex procurement documents -- ingesting hundreds of pages,
extracting structure, classifying content, and synthesizing actionable intelligence
for bid teams. Multi-pass LLM pipelines for high recall, domain-specific fine-tuning
on thousands of Swedish procurement Q&A pairs, and a conversational Q&A system with
grounded citations over source documents.

Full stack from infrastructure to frontend: Next.js, FastAPI, PostgreSQL, LLM
orchestration, document processing, Cloud Run, Terraform.

---

### Previously built: AI-powered shelf analytics (Loupe)

Designed and led development of a platform that let brands monitor product presentation,
pricing, and visibility across retail websites. The interesting technical problems:

**Distributed image processing** -- Apache Beam pipelines on Google Dataflow for
large-scale image ingestion, Vertex AI embeddings, and approximate nearest neighbor
(ANN) vector search for visual product matching. Custom parallelism control to
respect API rate limits, multi-stage processing with status-file orchestration.
[shelf-analytics-image-flows](https://github.com/panprices/shelf-analytics-image-flows)

**Vision-LLM product matching** -- When products lacked GTINs, we used vision
language models to visually match products across retailers. Batch processing at
scale with confidence-based filtering and database-backed task queuing.
[vlm-product-matching](https://github.com/panprices/vlm-product-matching)

**Production web crawling at scale** -- Playwright-based crawlers (Crawlee) on
Kubernetes with 10+ retailer-specific implementations, anti-bot handling, proxy
rotation, and HAR-based testing for reliability.
[shelf-analytics-scraper](https://github.com/panprices/shelf-analytics-scraper)

**Workflow orchestration** -- GCP Workflows chaining Dataflow jobs, Vertex Batch
predictions, and K8s jobs with callback-based coordination via Firestore.
[shelf-analytics-workflows](https://github.com/panprices/shelf-analytics-workflows)

**Data layer** -- FastAPI async backend with Stripe-inspired canonical log lines.
PostgreSQL with 870+ migrations spanning products, offers, images, embeddings, and
matching tasks.
[shelf_analytics_api](https://github.com/panprices/shelf_analytics_api) |
[panprices_db](https://github.com/panprices/panprices_db)

---

### Previously built: Distributed price intelligence (Panprices)

Before Loupe, built the data infrastructure that started it all -- a system that scraped
7+ price comparison sources across Europe (Google Shopping, Idealo, Pricerunner, Prisjakt,
Kelkoo, Kuantokusta, Geizhals). Async Python with typed Pydantic models, event-driven
via Cloud Pub/Sub, persisted to PostgreSQL + BigQuery, real-time sync to Firebase for
sub-second client updates. Each scraper as an independent Cloud Function with parallel
CI/CD via Cloud Build.

[sherlock_offer_scrapers](https://github.com/panprices/sherlock_offer_scrapers) |
[sherlock_db_functions](https://github.com/panprices/sherlock_db_functions) |
[sherlock_firebase](https://github.com/panprices/sherlock_firebase)

---

### Exploring

- [llm-self-hosting](https://github.com/t0mdicks0n/llm-self-hosting) -- Running open-weight models on ephemeral cloud GPUs via SkyPilot + vLLM
- [finetuning_llms](https://github.com/t0mdicks0n/finetuning_llms) -- LLM fine-tuning experiments
- [nanochat_learning](https://github.com/t0mdicks0n/nanochat_learning) -- Building a ChatGPT-style model from scratch

### Stack

Python, TypeScript, SQL, Go, C++ | GCP (Cloud Run, Dataflow, Vertex AI, Cloud Functions,
Pub/Sub, BigQuery, Workflows, Document AI) | PostgreSQL, Firebase | FastAPI, Next.js,
React | Apache Beam, Playwright, Terraform
