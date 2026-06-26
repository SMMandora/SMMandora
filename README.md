# Hi, I'm Shubham Mandora 👋

**Founding Engineer · Backend & AI Systems**

I build production backend infrastructure, distributed systems, and AI pipelines. Currently founding engineer at Vizzy Labs building real-time systems on AWS. Previously research at NYIT working on agentic AI and sensor data pipelines.

📍 Jersey City, NJ &nbsp;|&nbsp; 📧 shubhammandora220800@gmail.com &nbsp;|&nbsp; [LinkedIn](https://www.linkedin.com/in/shubhamm2208)

---

## What I Work With

**Languages:** Python · Go · TypeScript · JavaScript · SQL · Shell  
**Backend:** FastAPI · Django · Celery · WebSockets · Server-Sent Events · REST APIs  
**Data & Storage:** PostgreSQL · Redis · MongoDB · DynamoDB · pgvector · Airflow · pandas  
**AI/ML:** LangChain · LangGraph · RAG pipelines · Claude API · YOLOv8 · MediaPipe · scikit-learn · PyTorch  
**Infra:** AWS (EC2, S3, Lambda, SageMaker) · Docker · Kubernetes · GitHub Actions · CI/CD  
**Observability:** Prometheus · Grafana · OpenTelemetry · Jaeger · k6 · pytest · Playwright

---

## Projects

### [AI Code Review Agent](https://github.com/SMMandora/AI-Code-Review-Agent)
Autonomous GitHub PR review agent — single Docker container with a FastAPI webhook receiver, LangGraph state machine, and Postgres/pgvector as the only external dependency.
- HMAC-verified webhooks enqueued with sub-second 202; LangGraph graph fetches the diff, estimates cost, retrieves repo conventions via Voyage AI embeddings, then runs four parallel Claude check nodes (correctness, security, style, test coverage)
- p95 review time under 30s on a 200-line diff at under $0.50/review; gated by a hand-labeled PR eval suite (80%+ findings match)
- Configurable per-repo via `.codereview.yml`
- **Stack:** TypeScript · FastAPI · LangGraph · Claude API · pgvector · Docker

---

### [Real-Time Pub/Sub Chat Service](https://github.com/SMMandora/Real-time_Pub-Sub_Chat_Service_in_Go)
Horizontally scalable real-time chat backend in Go.
- Stateless WebSocket gateway replicas fan messages via Redis pub/sub; separate worker persists to Postgres
- Serves history, presence, typing indicators, auth, and rate limiting (30 msg/min Redis token bucket)
- Instrumented with Prometheus metrics and OpenTelemetry tracing to Jaeger; tested with testcontainers-go
- Kubernetes HPA autoscaling on active connections (min 2 / max 20); k6 load tested to 10k concurrent connections at p99 fan-out latency under 50ms
- **Stack:** Go · Redis · PostgreSQL · Prometheus · OpenTelemetry · Kubernetes

---

### [SLO Control Center](https://github.com/SMMandora/SLO-Control-Center)
End-to-end SLO observability stack with a Go orders-api, Prometheus recording rules, and dual-surface SLO dashboard.
- SLI, error budget, multi-window burn rate, and p95 latency computed as Prometheus recording rules
- Live state served through a Go BFF rendered in both a React (Vite + Tailwind + Recharts) SLO Control Center and a Grafonnet-generated Grafana dashboard — zero manual UI editing
- SLO defined as 99.9% availability over 28 days at 200ms p95; Prometheus rules unit-tested with promtool
- **Stack:** Go · Prometheus · Grafana · Grafonnet · React · k6

---

### [Online Proctoring Using AI](https://github.com/SMMandora/online-proctoring-using-ai)
Real-time AI proctoring system with a React/TypeScript frontend and FastAPI backend.
- MediaPipe face landmarking at ~15 FPS client-side; YOLOv8 object/multi-person detection, InsightFace ArcFace ID recheck, and Silero VAD server-side
- Gaze tracking with per-user 5-station calibration; head-pose, talking, tab-switch, and phone/book/laptop detection feeding a live suspicion score
- Proctor dashboard with evidence clips and Whisper transcription of flagged speech
- Hardened with Fernet-encrypted ID storage, JWT-secret boot enforcement, and per-IP login rate limiting
- **Stack:** TypeScript · React · FastAPI · YOLOv8 · MediaPipe · InsightFace · WebSocket

---

### [Sustainable City Management](https://github.com/SMMandora/sustainable-city-management)
Real-time data platform for Dublin city infrastructure.
- Ingests live DublinBikes, Sonitus noise-sensor, and OpenWeather feeds via Celery workers; serves over REST + Server-Sent Events to three live React dashboards (Vite + Leaflet + Recharts)
- Django 5 + DRF + PostgreSQL 16 + Redis 7 with health/readiness probes, structured JSON logging, and Grafana + Prometheus observability
- Local Kubernetes staging on kind behind nginx-ingress; GitHub Actions CI/CD; pytest integration, Playwright e2e, and k6 load tests
- **Stack:** Python · Django · PostgreSQL · Redis · Celery · React · Kubernetes

---

### [GloveSense](https://github.com/SMMandora/GloveSense)
Full-stack gesture recognition system built around an 8-channel ESP8266 sensor glove.
- FastAPI backend with WebSocket streaming; async sample-collection pipeline with pause/resume/abort
- Signal processing: baseline subtraction, spike removal, window averaging, per-window normalization
- Per-user Random Forest classifier trained on 15 ASL gestures; model persisted per user profile
- Arduino firmware (C++) triggering serial capture at 9600 baud; live Chart.js plots across 8 sensor channels
- **Stack:** Python · FastAPI · scikit-learn · WebSocket · Chart.js · C++ (Arduino)

---

## Experience

**Founding Engineer – Backend & Data** · Vizzy Labs, Inc · Aug 2025 – Present  
Production backend data infrastructure on AWS in Python. PostgreSQL, MongoDB, DynamoDB data modeling. Prometheus + Grafana observability and alerting. Reliability, testing frameworks, and CI/CD.

**Research Assistant** · New York Institute of Technology · Jan – Aug 2025  
Python data pipelines with Airflow-style orchestration. RAG-based semantic search with LangChain and pgvector. scikit-learn classification models (RF, SVM, MLP). Real-time sensor stream ingestion and visualization.

**Software Developer Intern** · IDZ Digital · Feb – Apr 2022  
Mobile games in Java, Kotlin, C#, and Unity shipped to App Store and Play Store across the full SDLC.

---

## Certifications

Google Advanced Data Analytics (Coursera) · AWS Certified Cloud Practitioner · Python Essentials (Cisco)
