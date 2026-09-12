# CKAD — 2-Week Study Plan

**Exam basics** (CNCF curriculum, Kubernetes v1.35): 5 domains, 15–20 performance-based tasks, 2 hours, 66% to pass. During the exam you can have one browser tab open to kubernetes.io/docs, kubernetes.io/blog, helm.sh/docs, and kustomize.io — so the plan below leans on *practicing with those docs open*, not memorizing everything.

| Domain | Weight |
|---|---|
| Application Environment, Configuration & Security | 25% |
| Application Design & Build | 20% |
| Application Deployment | 20% |
| Services & Networking | 20% |
| Application Observability & Maintenance | 15% |

Assumes ~2–3 hrs/day. You already have hands-on AKS experience, so skim anything below that's already second nature and shift that time to Security/RBAC, Kustomize, and Helm — the areas most candidates lose points on.

## Week 1 — Foundations + heaviest domains

**Day 1 — Setup & exam mechanics**
`kubectl` alias (`alias k=kubectl`), bash completion, vim config for YAML, imperative commands (`run`, `create`, `expose`), `--dry-run=client -o yaml` for scaffolding. Skim the full CNCF curriculum doc once for orientation.

**Day 2 — Application Design & Build (part 1)**
Pods, Deployments, DaemonSets, StatefulSets, Jobs, CronJobs. Multi-container patterns: sidecar, init, ambassador, adapter.

**Day 3 — Application Design & Build (part 2)**
Container images (write/modify Dockerfiles, multi-stage builds), volumes (emptyDir, hostPath, PVC/PV, ephemeral vs persistent).

**Day 4 — Environment, Config & Security (part 1)**
ConfigMaps, Secrets (as env vars, volumes), resource requests/limits, ResourceQuotas & LimitRanges, ServiceAccounts.

**Day 5 — Environment, Config & Security (part 2)**
SecurityContexts (pod & container level), capabilities, RBAC (Roles/RoleBindings/ClusterRoles), admission control basics, CRDs/Operators (conceptual — install/use one, e.g. `kubectl explain`).

**Day 6 — Services & Networking**
Service types (ClusterIP, NodePort, LoadBalancer), Ingress rules/routing, NetworkPolicies (default-deny + allow rules), DNS/service-discovery troubleshooting.

**Day 7 — Review + checkpoint**
Timed mixed quiz covering Days 2–6 (use KillerCoda or KodeKloud CKAD scenarios). Patch weak spots. Catch-up buffer if behind.

## Week 2 — Deployment/Observability + exam simulation

**Day 8 — Application Deployment (part 1)**
Rolling updates & rollbacks (`kubectl rollout`), deployment strategies (blue/green, canary via labels/services), Helm basics (install, upgrade, rollback, `--set`/values files).

**Day 9 — Application Deployment (part 2)**
Kustomize (bases, overlays, patches, `kustomization.yaml`).

**Day 10 — Observability & Maintenance**
Probes (liveness/readiness/startup), `kubectl top/describe/debug`, multi-container & previous-container logs, awareness of API deprecations (`kubectl api-resources`, `deprecations.md`).

**Day 11 — Full mock exam #1**
killer.sh session (2 come free with CKAD registration) or a KillerCoda full scenario set, timed at 2 hours. Review every miss.

**Day 12 — Targeted drilling**
Redo only the domains you missed on mock #1. Speed drills: imperative one-liners, doc-search speed (practice finding an example in kubernetes.io/docs in under 30 seconds).

**Day 13 — Full mock exam #2**
Second killer.sh session, timed. Build a short "final gap list" from remaining misses.

**Day 14 — Light review + exam**
Review only the final gap list, rehearse opening/bookmarking the allowed docs tabs, rest. Take the exam.

## Notes
- Register early enough that your 2 free killer.sh sessions are available before Day 11.
- Time management on exam day: ~6 min/task average: flag and skip anything stuck past that, come back at the end.
- If daily time runs under ~2 hrs some days, protect Days 4–5 (Security, 25% weight) and Day 9 (Kustomize) first — they're the most commonly under-practiced.
