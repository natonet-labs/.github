# NatoNet Labs

![Focus](https://img.shields.io/badge/Focus-Edge%20MLOps-blueviolet)
![Stack](https://img.shields.io/badge/Stack-K3s%20%7C%20NPU%20%7C%20Self--Hosted-333333)
![Infra](https://img.shields.io/badge/Infra-Cloud--Agnostic-orange)

Infrastructure-as-Code for Edge AI — building production-grade ML operations on physical silicon, away from cloud abstractions.

---

## Active Project

### [pdi-edge-mlops-core](https://github.com/natonet-labs/pdi-edge-mlops-core)
A 24-week hands-on roadmap implementing a cloud-agnostic MLOps stack on edge hardware.

![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Phase](https://img.shields.io/badge/Phase-1%20Foundation-blue)

**Stack:** LattePanda 3 Delta · DeepX DX-M1 (25 TOPS NPU) · K3s · GitHub Actions · Prometheus/Grafana

| Phase | Focus | Status |
|---|---|---|
| 1 — Foundation | OS provisioning, K3s cluster init, CI/CD handshake | 🔄 In Progress |
| 2 — Acceleration | DX-M1 K8s integration, model containerization, registry | ⏳ Upcoming |
| 3 — Observability | Prometheus/Grafana telemetry, load benchmarking, tunneling | ⏳ Upcoming |

---

## Repository Index

| Repo | Description |
|---|---|
| [pdi-edge-mlops-core](https://github.com/natonet-labs/pdi-edge-mlops-core) | 24-week Edge MLOps roadmap — K3s, NPU inference, IaC, observability |
| [edge-vision-lattepanda-3-delta-dx-m1](https://github.com/natonet-labs/edge-vision-lattepanda-3-delta-dx-m1) | Hardware bring-up docs for LattePanda 3 Delta + DeepX DX-M1 (archived reference) |
| [local-llm-rag-qdrant-ubuntu](https://github.com/natonet-labs/local-llm-rag-qdrant-ubuntu) | Local LLM + RAG pipeline with Qdrant on Ubuntu |
| [tailscale-pi-exit-node](https://github.com/natonet-labs/tailscale-pi-exit-node) | Tailscale exit node configuration on Raspberry Pi |

---

## Stack Snapshot

```
Edge Compute    →  LattePanda 3 Delta (Intel N5105) × 2 nodes
AI Acceleration →  DeepX DX-M1 (25 TOPS, 4GB LPDDR5) on Node 01
Orchestration   →  K3s (lightweight Kubernetes)
CI/CD           →  GitHub Actions + self-hosted runners
Observability   →  Prometheus / Grafana
Networking      →  Tailscale (secure overlay)
OS              →  Ubuntu 24.04 LTS
```
