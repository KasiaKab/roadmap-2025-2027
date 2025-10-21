#  ✅ Completed Tasks

## M00 — Foundations
- [x] 2025-10-05 Add `.gitignore` for IntelliJ
- [x] 2025-10-06 Study C4 model theory
- [x] 2025-10-07 Create `C4-context.mmd` + `C4-container.mmd`
- [x] 2025-10-08 Study ADR structure and examples + Add `ADR-001-monolith-first.md` (accepted) + Create `coworkly-api` repo
- [x] 2025-10-09 Set up base project structure + configure local PostgreSQL (Docker + dev.yml) + add ADR-002 (accepted)
- [x] 2025-10-10 Implement JPA entities (`Resource`, `Booking`) and repositories  
  &nbsp;&nbsp;→ Add Flyway dependencies and migration `V1__init.sql`  
  &nbsp;&nbsp;→ Verified DB connection and migration execution  
  &nbsp;&nbsp;→ Confirmed table creation (`resource`, `booking`) via Docker PostgreSQL
- [x] 2025-10-11 Verify BookingRepository with @DataJpaTest  
  &nbsp;&nbsp;→ Added `BookingRepositoryTest.java`  
  &nbsp;&nbsp;→ Confirmed Flyway migration and entity mapping validity
- [x] 2025-10-12 API layer scaffolding  
  → Added API contract draft (`designs/api-contract.mmd`)  
  → Implemented DTOs (`ResourceDto`, `TimeSlotDto`, `AvailabilitySlotDto`, `BookingDto`, `BookingRequest`, `BookingResponse`)  
- [x] 2025-10-13 Implemented mappers and accepted ADR-003  
  → Added `ResourceMapper`, `TimeSlotMapper`, `BookingMapper`  
  → Added `ADR-003-rest-design-plan.md` (API structure defined, controllers pending)
- [x] 2025-10-16 Implemented exception handling and booking service logic  
  &nbsp;&nbsp;→ Added domain exceptions (`NotFoundException`, `SlotAlreadyBookedException`)  
  &nbsp;&nbsp;→ Implemented `BookingService` and `ResourceService` with validation checks
- [x] 2025-10-17 Implemented REST controllers for core resources  
  &nbsp;&nbsp;→ Added `BookingController` and `ResourceController`  
  &nbsp;&nbsp;→ Integrated DTO mapping 
  &nbsp;&nbsp;→ Verified end-to-end flow (controller → service → repository)  
  &nbsp;&nbsp;→ Updated sequence & API diagrams (`designs/api-sequence-booking.png`, `designs/api-layer-architecture.png`)
- [x] 2025-10-19 Added minimal `GlobalExceptionHandler`  
  &nbsp;&nbsp;→ Unified JSON format `{code, message}`  
  &nbsp;&nbsp;→ Mapped `NotFoundException` → **404**, `SlotAlreadyBookedException` → **409**, and generic → **500**
- [x] 2025-10-20 Added Flyway migration `V2__add_booking_time_slot_fk.sql` + entity sync  
  &nbsp;&nbsp;→Added `@PrePersist` default status
- [x] 2025-10-21 Added Flyway migration `V3__add_idempotency_key_to_booking.sql`