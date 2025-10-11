# Week 01 — 6–12 Oct 2025
**Focus:** Establishing the architectural foundation — C4 diagrams, domain model design, and initial database migration.

---

## ✅ Deliverables
- ADR-002 finalized (PostgreSQL + Flyway, verified)
- Entities `Resource` and `Booking` implemented
- Migration `V1__init.sql` executed successfully
- Repository test `BookingRepositoryTest` (✅ passed)

---

## 📝 Technical Notes
- Confirmed that `@DataJpaTest` + H2 works for isolated DB tests.
- Verified Flyway migration consistency with PostgreSQL via Docker.

---

## ⏭️ Next
- Prepare ADR-003 — REST API design & error format.
- Define OpenAPI draft (`/resources`, `/bookings`).
- Plan week-2 deliverables toward API layer.

---
Last updated: 2025-10-11