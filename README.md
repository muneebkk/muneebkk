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

ECHO, a fraud detection platform built from an empty repo by a four-person team over 16 weeks. It checks for fraud in two passes, a fast cheap one first and a slower expensive one only when needed, which is now patent pending with me on the filing. I owned the pipeline that moves events through the system and the contracts between services, so nothing gets lost or counted twice when something fails. Demoed to 400+ staff at RBC AmpExpo and going into production.

### Technical Lead · SFU Blueprint (Richmond Poverty Reduction Coalition)
`Jan 2026 - Apr 2026`

Led six developers building a membership platform for a poverty-reduction nonprofit. Split the app into separate services on AWS, made the slow database queries fast, and set up the deploy pipeline around it.

### Backend Software Engineer Intern · OpenQQuantify
`Aug 2025 - Dec 2025`

Event processing on Kafka for multiple customers on shared infrastructure. Tuned the system to survive sudden traffic spikes, and added logging that made it possible to trace a single request across every instance it touched.

### Full Stack Developer · CJSF Radio
`Apr 2025 - Jul 2025`

Moved an old single-block PHP/Laravel broadcast platform onto containers. Fixed scheduler bugs where two things ran at once and clashed, kept encoding failures from taking playback down with them, and built listener analytics.

---

## Projects

### Memory-Constrained DAG Scheduler
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Gurobi](https://img.shields.io/badge/MILP_/_Gurobi-A11D21?style=flat-square)
![1st of 220+](https://img.shields.io/badge/1st_of_220+-B45309?style=flat-square)

A C++ scheduler that decides what order to run jobs in when memory is capped. Tried three approaches and went with beam search, since the one that guarantees the perfect answer could run forever. Checked my results against the mathematically optimal solver to confirm the schedules held up, and cut peak memory 40% versus the baseline. Presented it to Huawei Research engineers at their Vancouver HQ.

### [CaseComp.ca](https://casecomp.ca)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white)
![Live](https://img.shields.io/badge/live-1,200+_users-0F766E?style=flat-square)

A case competition platform running across 10+ universities. Each school's data is walled off inside the database itself rather than by application code, so there's no way for a developer to forget the check and leak one school's data to another. Payments are built so that if Stripe sends the same event twice, nobody gets charged twice.

### Other work

**[HeatSpace](https://github.com/Ekanshthegreat/SafeSpace)** · *Next.js, Flask, OpenCV, NumPy/SciPy, Redis*
Hackathon winner. Reads a 3D floor plan, simulates how heat spreads through the rooms, and works out where to put the heaters for even coverage. Caching keeps a full multi-room simulation under two seconds.

**[WebTraceAI](https://github.com/muneebkk/webtraceai)** · *Next.js, Flask, OpenCV, scikit-learn*
Detects whether a web design was AI-generated. Hand-labeled a dataset of 200+ screenshots and compared a few models. Random Forest landed around 80% accuracy in under half a second.

**Horizon Expeditions** · *Backend Developer, Aug 2024 - Jan 2025*
Backend features for team management and real-time tracking.

---

## Skills

**Languages**

![Java](https://img.shields.io/badge/Java-E76F00?style=flat-square&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

**Backend**

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
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

**ML and monitoring**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)

**Systems and tooling**

Concurrency, message queues, performance profiling, query optimization, SQLAlchemy, VisualVM, k6

---

## Elsewhere

2x MLH hackathon winner. Peer tutor at SFU, 100+ students through data structures and algorithms. Community advisor for 200+ residents in student housing, which turns out to have more in common with debugging a distributed system than you'd expect.
