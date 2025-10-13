# Roadmap 2025–2027

**Goal:** Build full-stack engineering foundations — from Java & Spring Boot to DevOps & AWS.  
This repository documents progress, milestones, architecture decisions, and learning artifacts along the way.

---

## 🗺️ Overview
This roadmap follows a multi-stage engineering path, focusing on both software design and cloud infrastructure skills.

| Phase | Focus | Period |
|-------|--------|------------------|
| **M00** | Architecture-First Monolith | **Oct – Dec 2025 (10 weeks)** |
| **M05** | IT & Networking Foundations | **Dec 2025 – Jan 2026 (2 weeks)** |
| **M10** | DevOps Fundamentals (CI/CD, Docker, GitHub Actions, Jenkins intro) | **Jan – Apr 2026 (12–14 weeks)** |
| **M20** | AWS + Terraform (Cloud Practitioner + IaC) | **Apr – Jul 2026 (12–14 weeks)** |
| **M25** | Automation & Config Mgmt (Python + Ansible) | **Jul – Aug 2026 (6 weeks)** |
| **M30** | Cloud Core (K8s + Helm + Monitoring + Logging) | **Sep 2026 – Jan 2027 (18 weeks)** |
| **M40** | Security + FinOps + AWS SAA Certification | **Feb – Jun 2027 (20 weeks)** |

---

## 🗂️ Repository Structure
The repository is organized as follows:

```text
roadmap-2025-2027/
├─ README.md                  → overview and structure
├─ engineering-log/           → daily or weekly progress notes
├─ milestones/                → key goals & deliverables per phase
├─ decisions/                 → ADRs (Architecture Decision Records)
├─ designs/                   → C4, ERD, and pipeline diagrams
└─ tasks/                     → backlog and completed tasks
```
---

## 📈 Progress Tracking
 [Engineering Log](engineering-log/) – daily project updates  
 [Milestones](milestones/) – deliverables and success criteria  
 [Backlogs](tasks/) – scoped task lists per phase  
 [Architecture Decisions](decisions/) – design trade-offs and context  
 [Designs](designs/) – C4, network, and infrastructure diagrams

---

## 🧩 Project Context: Coworkly

All roadmap milestones are implemented through a single evolving system — **Coworkly**,  
a Spring Boot application for coworking room reservations.

Coworkly acts as a practical case study for my entire DevOps & Cloud journey:
- **M00:** Architecture-first monolith (Spring Boot + PostgreSQL + Docker)
- **M05:** Networking foundations (VPC + CIDR + DNS basics)
- **M10–M40:** CI/CD, AWS, Terraform, Automation, K8s, Observability, and Security

Each milestone adds a new engineering layer — from clean code and data design to  
cloud deployment and cost-aware production readiness.

📁 The application lives in a separate repository: [`coworkly-api`](https://github.com/KasiaKab/coworkly-api)


---
Last updated: 2025-10-13
