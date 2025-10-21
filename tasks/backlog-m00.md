# Backlog — M00: Architecture-First Monolith

🎯 **Goal:**  
Build the first production-ready core of Coworkly — a Spring Boot monolith with solid architecture, data model, and observability.

---

## 🧩 Architecture Decisions (ADRs)
- [x] ADR-001 — Monolith-First approach
- [x] ADR-002 — Database choice: PostgreSQL + Flyway (dev via Docker, Flyway pending)
- [x] ADR-003 — REST design & error format 
- [ ] ADR-004 — Security baseline (JWT later)
- [ ] ADR-005 — CI/CD tool: GitHub Actions

---

## ⚙️ Implementation
### 1️⃣ Core setup
- [x] Create `coworkly-api` repo (Spring Boot 3 + Java 21)
- [x] Add `.gitignore`, `.editorconfig`, and base structure
- [x] Define entities: Resource, Booking
- [x] Add Flyway migration `V1__init.sql`
- [x] Add Flyway migration `V2__add_booking_time_slot_fk.sql`
- [x] Add Flyway migration `V3__add_idempotency_key_to_booking.sql`
- [x] Basic repository test (@DataJpaTest)

### 🧱 System Design
- `C4-context.mmd` – high-level view
- `C4-container.mmd` – backend major container
- `erd-booking.mmd` – relational model
- `api-layer-architecture.png` – REST layer interaction
- `api-sequence-booking.png` – booking request flow
- `architecture-overlap.png` – architecture styles overlap (internal note)

### 2️⃣ REST API
- [x] API contract draft (`designs/api-contract.mmd`) — endpoints (`/resources`, `/bookings`, `/resources/{id}/availability`)
- [x] DTOs: `ResourceDto`, `TimeSlotDto`, `AvailabilitySlotDto`, `BookingDto`, `BookingRequest`, `BookingResponse`
- [x] Mappers: `ResourceMapper`, `TimeSlotMapper`, `BookingMapper`
- [x] Controllers: `ResourceController`, `BookingController`
- [x] Global error handler (`GlobalExceptionHandler`) + consistent `{code,message}` JSON payload
- [x] Services: `ResourceService`, `BookingService` (with collision check)
- [X] Idempotency-Key handling in `POST /bookings` (filter + persistence)
- [ ] `@WebMvcTest` for booking flow (persistent key + 200/201 logic)
- [ ] OpenAPI spec update for controllers + errors
- [ ] Sequence diagram `api-sequence.mmd`

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

🗓️ *Updated:* 2025-10-21  