# NatoNet Labs

![Focus](https://img.shields.io/badge/Focus-Edge%20MLOps-blueviolet)
![Stack](https://img.shields.io/badge/Stack-K3s%20%7C%20NPU%20%7C%20Self--Hosted-333333)
![Infra](https://img.shields.io/badge/Infra-Bare%20Metal%2C%20No%20Cloud-orange)

Infrastructure-as-Code for Edge AI — building production-grade ML operations on physical silicon, away from cloud abstractions.

---

## Active Projects

### [bare-metal-mlops-sandbox](https://github.com/natonet-labs/bare-metal-mlops-sandbox)
A high-fidelity engineering environment for learning real-world MLOps on bare metal hardware — no managed cloud services, no abstractions.

![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Phase](https://img.shields.io/badge/Phase-1%20Foundation-blue)

**Stack:** LattePanda 3 Delta × 2 · DeepX DX-M1 (25 TOPS NPU) · K3s · GitHub Actions · Prometheus/Grafana

| Phase | Focus | Status |
|---|---|---|
| 1 — Foundation | OS provisioning, K3s cluster init, CI/CD handshake | In Progress |
| 2 — Acceleration | DX-M1 K8s integration, model containerization, local registry | Upcoming |
| 3 — Observability | Prometheus/Grafana telemetry, load benchmarking, secure tunneling | Upcoming |

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
| [edge-vision-lattepanda-3-delta-dx-m1](https://github.com/natonet-labs/edge-vision-lattepanda-3-delta-dx-m1) | Hardware bring-up docs for LattePanda 3 Delta + DeepX DX-M1 (archived reference) |
| [local-llm-rag-qdrant-ubuntu](https://github.com/natonet-labs/local-llm-rag-qdrant-ubuntu) | Local LLM + RAG pipeline with Qdrant on Ubuntu |
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
