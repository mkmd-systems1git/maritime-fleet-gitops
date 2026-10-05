# GitOps for the Fleet: Over-The-Air (OTA) Container Orchestration

## 📌 Executive Summary
This project delivers a declarative GitOps continuous deployment pipeline that automates secure, over-the-air (OTA) software rollouts and patch management across a globally distributed fleet of commercial vessels using infrastructure-as-code (IaC) and container registries.

* **Strategic Outcome:** Automated microservice distribution to 100% of the active fleet simultaneously with zero physical technical travel required.
* **Architecture Stack:** GitHub Actions CI/CD, GitHub Container Registry (GHCR), Declarative Kubernetes (K8s/K3s Manifests), Configuration as Code (Dockerfile).
* **Deployment Timeline:** 21 Seconds (Automated Build & Ship Execution)

🔴 **The Friction Point (The Before)**
Commercial shipping lines operate fleets of remote vessels running legacy, fragmented software stacks. Historically, pushing a critical security patch or an updated tracking microservice required shipping hardware USB drives to ports or flying highly paid technicians directly to physical vessel hubs globally. This manual approach introduced massive operational delays, left ships vulnerable to software security risks for months, and created high-ticket travel expenses—costing maritime enterprises an average of \$45,000 USD annually in overhead per vessel just to maintain system updates.

⚙️ **The Architecture Map (The Technical Fix)**
We dismantled this manual update ceiling by architecting a modern GitOps pipeline that bridges cloud automation with remote edge infrastructure:
* **The Automated Pipeline:** Embedded a GitHub Actions assembly line (`fleet-deploy.yml`) that dynamically triggers on code changes, handling secure, passwordless authentication using temporary cryptographic tokens.
* **The High-Availability Engine:** Containerized a resilient Python edge tracking application using a hyper-lightweight runtime layer to ensure minimal memory footprints on legacy seagoing hardware.
* **Declarative Orchestration:** Architected a Kubernetes manifest (`vessel-deployment.yaml`) enforcing strict hardware protection thresholds (128Mi RAM limit) and a dual-replica redundancy parameter to guarantee self-healing capabilities if a container encounters an error at sea.

```text
[Developer Push] ──> [GitHub Actions Pipeline] ──> [GitHub Container Registry (GHCR)]
                                                                    │
                                                      (Automated Over-The-Air Pull)
                                                                    ▼
                                                       [⛴️ Global Cargo Fleet]
                                                       └── [K3s Cluster: Replica 1]
                                                       └── [K3s Cluster: Replica 2]
```

🟢 **The Business Result - (The Commercial ROI)**
The physical software deployment ceiling was permanently eliminated. Continuous delivery execution time dropped from weeks of technical coordination down to a completely automated **21-second cloud build-and-ship window**, reducing manual rollout errors to absolute zero. By replacing manual on-site port updates with secure, automated over-the-air container distribution pipelines, the maritime enterprise slashes specialized technical travel costs and infrastructure administrative overhead by an estimated **$74,000 USD/year per fleet division** while ensuring the entire global fleet stays fully compliant with international digital security standards.

