# Muneeb Kamran


[![Email](https://img.shields.io/badge/mmk28@sfu.ca-0F766E?style=flat-square&logo=gmail&logoColor=white)](mailto:mmk28@sfu.ca)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-1E4E79?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/muneeb-kamran-0a345722a)
![Vancouver](https://img.shields.io/badge/Vancouver,_BC-3F3F46?style=flat-square&logo=googlemaps&logoColor=white)

---

## About

Third-year CS student at Simon Fraser University, Minor in Statistics, graduating May 2028. Grew up between Pakistan and Dubai, now in Vancouver.

Open to Winter, Summer, and Fall 2027 internships. Most interested in infrastructure, platform, and ML serving teams.

---

## Experience

### Software Engineer Intern · Royal Bank of Canada, Amplify Program
`May 2026 - Aug 2026`

ECHO, a patent-pending fraud detection platform that reads call transcripts and classifies them against a taxonomy of threat indicators. The interesting constraint was cost: running an LLM over every call at bank scale is not affordable, so the system is a two-stage cascade where a cheap embedding-based classifier gates the expensive model and only escalates what looks suspicious. I owned the orchestration layer and the service contracts, which meant thinking hard about idempotency, since a pipeline that re-ingests on failure has to be safe to rerun. Built from an empty repo by a four-person team over 16 weeks, deployed on OpenShift, demoed at RBC AmpExpo, and going into production.

### Technical Lead · SFU Blueprint (Richmond Poverty Reduction Coalition)
`Jan 2026 - Apr 2026`

Led six developers building a membership platform for a poverty-reduction nonprofit. Most of the job was architectural judgment rather than code: splitting the system into services so pairs could ship in parallel, deciding against Kafka once load projections showed a managed queue would do, and refusing to hand a volunteer team infrastructure they'd have to be on-call for. The rest was the usual, chasing down N+1 queries and building a deploy pipeline that could roll itself back.

### Backend Software Engineer Intern · OpenQQuantify
`Aug 2025 - Dec 2025`

Multi-tenant event processing on Kafka, where the core design question is what you partition on. Partitioning by tenant gives you throughput and isolation but gives up global ordering, which was the right trade here. Spent most of my time on the things that only show up under load, profiling thread contention in the JVM and replacing unbounded thread creation with a properly sized pool, and on making incidents traceable by keying structured logs to message IDs instead of grepping across instances.

### Full Stack Developer · CJSF Radio
`Apr 2025 - Jul 2025`

Migrated a PHP/Laravel monolith serving live radio into separate services, with the goal of making sure an encoding failure couldn't take playback down with it. The best bug of the term was a TOCTOU race causing intermittent silent shows, fixed by making broadcast slot claiming atomic at the database level rather than in application logic. Also built listener analytics, batching writes through Redis rather than hammering PostgreSQL per event.

---

## Projects

### [CaseComp.ca](https://casecomp.ca)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white)
![Live](https://img.shields.io/badge/live-2,000+_users-0F766E?style=flat-square)

A live case competition platform used across a dozen universities, which makes it a multi-tenant system where a leak between tenants is the worst thing that could happen. So isolation lives in PostgreSQL row-level security driven by JWT claims rather than in application code, because a rule the database enforces can't be forgotten by a developer in a hurry. Payments follow the same principle: Stripe guarantees at-least-once webhook delivery, so the handlers are idempotent and deduplicated on event ID, and duplicate delivery is a non-event rather than a double charge.

### Coalesce
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-244C5A?style=flat-square&logo=grpc&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

A batch inference server in Go, built to understand how serving systems actually earn their throughput. Model inference is far more efficient on batches than on single requests, so the server holds arriving requests briefly and coalesces them into batches bounded by either size or deadline, which is the tradeoff at the heart of every real serving stack: latency for efficiency. The other half of the problem is what happens when demand exceeds capacity, handled with bounded queues and admission control so the server sheds load deliberately instead of collapsing. Benchmarked against fixed batching under burst traffic to confirm the dynamic approach is worth its complexity.

### ML Observability Platform
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

Models fail quietly. Nothing throws, the latency looks fine, and the predictions slowly stop meaning what they used to because the world moved and the training data didn't. This is monitoring for that failure mode: ingest prediction logs, measure how far the live feature distribution has drifted from the training baseline using PSI and KL divergence, and alert on it the same way you'd alert on an SLO burn rate. Drift past a threshold can fire a retraining trigger automatically, which is the part that makes it a platform rather than a dashboard.

### Huawei Challenge | Memory-Constrained DAG Scheduler
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Gurobi](https://img.shields.io/badge/MILP_/_Gurobi-A11D21?style=flat-square)
![1st of 220+](https://img.shields.io/badge/1st_of_220+-B45309?style=flat-square)

Scheduling a dependency graph of jobs under a hard memory ceiling, which is NP-hard and therefore a question about what you're willing to give up. Branch-and-bound gives you the optimal schedule and no bound on how long it takes to find it, so I went with beam search guided by critical-path priority, then validated the output against MILP solutions to confirm the approximation held up in practice. Won the Huawei challenge and presented it to their research engineers in Vancouver.

### Other work

**[HeatSpace](https://github.com/Ekanshthegreat/SafeSpace)** · *Next.js, Flask, OpenCV, NumPy/SciPy, Redis*
Hackathon winner. Parses 3D floor plans with OpenCV and graph segmentation, then runs Gaussian heat diffusion solvers to place heaters for balanced airflow. Redis caching keeps a multi-room simulation under two seconds.

**[WebTraceAI](https://github.com/muneebkk/webtraceai)** · *Next.js, Flask, OpenCV, scikit-learn*
An AI detector for web design. Hand-labeled a dataset of 200+ screenshots and benchmarked several classifiers. Random Forest landed around 80% accuracy at sub-500ms inference.

---

## Skills

**Languages**

![Java](https://img.shields.io/badge/Java-E76F00?style=flat-square&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

**Backend**

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-244C5A?style=flat-square&logo=grpc&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![OpenAPI](https://img.shields.io/badge/OpenAPI-6BA539?style=flat-square&logo=openapiinitiative&logoColor=white)

**Cloud and infra**

![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazonwebservices&logoColor=white)
![OpenShift](https://img.shields.io/badge/OpenShift-EE0000?style=flat-square&logo=redhatopenshift&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Keycloak](https://img.shields.io/badge/Keycloak/OIDC-4D4D4D?style=flat-square&logo=keycloak&logoColor=white)

**ML and observability**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![SentenceTransformers](https://img.shields.io/badge/SentenceTransformers-FFB000?style=flat-square)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)

**Distributed systems and tooling**

Concurrency, thread pools, message queues, backpressure, performance profiling, query optimization, SQLAlchemy, VisualVM, pprof, k6

---

## Elsewhere

2x MLH hackathon winner. Peer tutor at SFU, 100+ students through data structures and algorithms. Community advisor for 200+ residents in student housing, which turns out to have more in common with debugging a distributed system than you'd expect.
