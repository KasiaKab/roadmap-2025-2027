# M00 — Architecture-First Monolith (Oct–Nov 2025)

**Goal**  
Build a monolith-first Spring Boot core for the *Coworkly* with focus on architecture, domain, and operability.

**Scope**
- Spring Boot + Postgres + Flyway
- Core domain: Resource, TimeSlot, Booking
- Actuator + Micrometer (health, metrics)
- Docker Compose (app + Postgres)
- 3–4 ADRs (Monolith, Database, CI, Security)

**Deliverables**
- Running app (local + CI)
- C4 and ERD diagrams in `/designs`
- ADRs in `/decisions`
- README with goals and metrics
- Tagged release `v0.1.0` + short demo video

**Success Criteria**
- App builds and runs locally
- At least one domain endpoint working
- Metrics exposed via Actuator
- README updated with architecture overview