# Backlog — M0: Architecture-First Monolith (Oct–Nov 2025)

🎯 **Goal:**  
Build the first production-ready core of Coworkly — a Spring Boot monolith with solid architecture, data model, and observability.

---

## 🧩 Architecture Decisions (ADRs)
- [ ] ADR-0001 — Monolith-First approach
- [ ] ADR-0002 — Database choice: PostgreSQL + Flyway
- [ ] ADR-0003 — REST design & error format
- [ ] ADR-0004 — Security baseline (JWT later)
- [ ] ADR-0005 — CI/CD tool: GitHub Actions

---

## ⚙️ Implementation
### 1️⃣ Core setup
- [ ] Create `coworkly-api` repo (Spring Boot 3 + Java 21)
- [ ] Add `.gitignore`, `.editorconfig`, and base structure
- [ ] Define entities: Resource, TimeSlot, Booking
- [ ] Add Flyway migration `V1__init.sql`
- [ ] Basic repository test (@DataJpaTest)

### 2️⃣ REST API
- [ ] Add `/resources` and `/bookings` endpoints
- [ ] Support idempotency-key for POST /bookings
- [ ] Global error handler + consistent JSON payload
- [ ] @WebMvcTest for one controller

### 3️⃣ Observability & Docker
- [ ] Enable Actuator (health/info/metrics)
- [ ] Add Micrometer + JSON logging with traceId
- [ ] Write Dockerfile + docker-compose (app + Postgres)
- [ ] Spring profiles: `dev` (H2), `local` (Postgres)

### 4️⃣ Release
- [ ] Update README (architecture, run guide)
- [ ] Record short demo (3–5 min)
- [ ] Tag release `v0.1.0` and link to M0 milestone

---

🗓️ *Updated:* 2025-10-05  