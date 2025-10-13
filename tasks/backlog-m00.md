# Backlog — M00: Architecture-First Monolith (Oct–Nov 2025)

🎯 **Goal:**  
Build the first production-ready core of Coworkly — a Spring Boot monolith with solid architecture, data model, and observability.

---

## 🧩 Architecture Decisions (ADRs)
- [x] ADR-001 — Monolith-First approach
- [x] ADR-002 — Database choice: PostgreSQL + Flyway (dev via Docker, Flyway pending)
- [ ] ADR-003 — REST design & error format
- [ ] ADR-004 — Security baseline (JWT later)
- [ ] ADR-005 — CI/CD tool: GitHub Actions

---

## ⚙️ Implementation
### 1️⃣ Core setup
- [x] Create `coworkly-api` repo (Spring Boot 3 + Java 21)
- [x] Add `.gitignore`, `.editorconfig`, and base structure
- [x] Define entities: Resource, Booking
- [x] Add Flyway migration `V1__init.sql`
- [x] Basic repository test (@DataJpaTest)

### 🧱 System Design
- [x] Study C4 model (Context + Container)
- [x] Create `C4-context.mmd`
- [x] Create `C4-container.mmd`
- [x] Design ERD (`erd-booking.mmd`)

### 2️⃣ REST API
- [x] API contract draft (`designs/api-contract.mmd`) — endpoints (`/resources`, `/bookings`, `/resources/{id}/availability`)
- [x] DTOs: `ResourceDto`, `TimeSlotDto`, `AvailabilitySlotDto`, `BookingDto`, `BookingRequest`, `BookingResponse`
- [x] Mappers: `ResourceMapper`, `TimeSlotMapper`, `BookingMapper`
- [ ] Controllers: `ResourceController`, `BookingController`
- [ ] @WebMvcTest for one controller
- [ ] Idempotency-Key handling in `POST /bookings` (service + persistence)
- [ ] Global error handler + consistent JSON payload

### 3️⃣ Observability & Docker
- [ ] Enable Actuator (health/info/metrics)
- [ ] Add Micrometer + JSON logging with traceId
- [x] Docker Compose: Postgres (local dev)
- [x] Spring profiles: `dev` (Postgres), `no-db` (API-only)

### 4️⃣ Release
- [ ] Update README (architecture, run guide)
- [ ] Record short demo (3–5 min)
- [ ] Tag release `v0.1.0` and link to M0 milestone

---

🗓️ *Updated:* 2025-10-13  