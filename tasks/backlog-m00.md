# Backlog — M00: Architecture-First Monolith (Oct–Nov 2025)

🎯 **Goal:**  
Build the first production-ready core of Coworkly — a Spring Boot monolith with solid architecture, data model, and observability.

---

## 🧩 Architecture Decisions (ADRs)
- [x] ADR-001 — Monolith-First approach
- [ ] ADR-002 — Database choice: PostgreSQL + Flyway
- [ ] ADR-003 — REST design & error format
- [ ] ADR-004 — Security baseline (JWT later)
- [ ] ADR-005 — CI/CD tool: GitHub Actions

---

## ⚙️ Implementation
### 1️⃣ Core setup
- [x] Create `coworkly-api` repo (Spring Boot 3 + Java 21)
- [x] Add `.gitignore`, `.editorconfig`, and base structure
- [ ] Define entities: Resource, TimeSlot, Booking
- [ ] Add Flyway migration `V1__init.sql`
- [ ] Basic repository test (@DataJpaTest)

### 🧱 System Design
- [x] Study C4 model (Context + Container)
- [x] Create `C4-context.mmd`
- [x] Create `C4-container.mmd`
- [ ] Design ERD (`erd-booking.mmd`)

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

🗓️ *Updated:* 2025-10-08  