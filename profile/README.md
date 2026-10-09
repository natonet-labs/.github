# NatoNet Labs

![Focus](https://img.shields.io/badge/Focus-Edge%20MLOps-blueviolet)
![Stack](https://img.shields.io/badge/Stack-K3s%20%7C%20NPU%20%7C%20Self--Hosted-333333)
![Infra](https://img.shields.io/badge/Infra-Bare%20Metal%2C%20No%20Cloud-orange)

Infrastructure-as-Code for Edge AI — building production-grade ML operations on physical silicon, away from cloud abstractions.

---

## Active Projects

### [bare-metal-mlops-sandbox](https://github.com/natonet-labs/bare-metal-mlops-sandbox)
A high-fidelity engineering environment for learning real-world MLOps on bare metal hardware — no managed cloud services, no abstractions.

![Status](https://img.shields.io/badge/Status-Concluded-blue)
![Phase](https://img.shields.io/badge/Reached-Phase%202.7-brightgreen)

**Stack:** LattePanda 3 Delta × 2 · DeepX DX-M1 (25 TOPS NPU) · K3s · GitHub Actions · Prometheus/Grafana

| Phase | Focus | Status |
|---|---|---|
| 1 — Foundation | OS provisioning, K3s cluster, DX-M1 NPU bring-up, local registry, Prometheus/Grafana, CI/CD | Complete |
| 2 — Acceleration & Serving | Two more NPU inference services (four total), model versioning, rollback, containerized workload, load-test baseline | Complete through 2.7 |
| 3 — Observability & Scale | Alerting, autoscaling, automated rollback, drift detection, failure simulation | Deferred |

Concluded June 2026. The cluster keeps running as the deployment target for application-layer work.

---

### Driveway Counter System

A production edge-AI system that counts driveway entries and exits 24/7. YOLOv8m inference runs entirely on a Hailo-8 NPU at 15 FPS / 7% CPU; an hourly sync pushes counts to a Cloudflare Workers dashboard accessible from anywhere without exposing the Pi to the internet.

**Stack:** Raspberry Pi 5 · Hailo-8 AI HAT (26 TOPS) · YOLOv8m · Python · Cloudflare Workers KV

| Repo | Role |
|---|---|
| [driveway-counter](https://github.com/natonet-labs/driveway-counter) | Pi-side — GStreamer + Hailo inference, polygon zone tracking, daily JSON reports, hourly KV sync |
| [driveway-metrics](https://github.com/natonet-labs/driveway-metrics) | Cloudflare Worker — KV storage, Bearer-auth ingest API, live dashboard with 30-day history |

---

## Repository Index

| Repo | Description |
|---|---|
| [bare-metal-mlops-sandbox](https://github.com/natonet-labs/bare-metal-mlops-sandbox) | Bare metal Edge MLOps — K3s cluster, NPU inference, IaC, observability |
| [driveway-counter](https://github.com/natonet-labs/driveway-counter) | RPi 5 + Hailo-8 driveway vehicle counter — YOLOv8m at 15 FPS, 7% CPU |
| [driveway-metrics](https://github.com/natonet-labs/driveway-metrics) | Cloudflare Workers backend — KV ingest, live dashboard, 30-day history |
| [local-llm-rag-qdrant-macos](https://github.com/natonet-labs/local-llm-rag-qdrant-macos) | Local LLM + RAG pipeline with Ollama and Qdrant on a Mac mini M4 |
| [local-llm-rag-qdrant-ubuntu](https://github.com/natonet-labs/local-llm-rag-qdrant-ubuntu) | Local LLM + RAG pipeline with Qdrant on Ubuntu |
| [local-llm-rag-chromadb-rpi5](https://github.com/natonet-labs/local-llm-rag-chromadb-rpi5) | Local RAG chatbot on Raspberry Pi 5 with Ollama and ChromaDB |
| [tailscale-pi-exit-node](https://github.com/natonet-labs/tailscale-pi-exit-node) | Tailscale exit node configuration on Raspberry Pi |

---

## Stack Snapshot

```
Edge Compute      →  LattePanda 3 Delta (Intel N5105) × 2 nodes
                     Raspberry Pi 5 (8 GB)
AI Acceleration   →  DeepX DX-M1 (25 TOPS, 4GB LPDDR5) on panda-control
                     Hailo-8 AI HAT (26 TOPS, PCIe) on RPi 5
Orchestration     →  K3s (lightweight Kubernetes)
CI/CD             →  GitHub Actions + self-hosted runners
Registry          →  Private local Docker registry (on-cluster)
Observability     →  Prometheus / Grafana (on-cluster)
Edge Serverless   →  Cloudflare Workers + KV
Networking        →  Tailscale (secure overlay)
OS                →  Ubuntu 24.04 LTS · Raspberry Pi OS 64-bit (Debian Trixie)
```
