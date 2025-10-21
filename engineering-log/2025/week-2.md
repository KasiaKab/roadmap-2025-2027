# Week 02 — 13–21 Oct 2025
**Focus:** Building the REST API layer with consistent error handling and idempotent booking creation.

---

## ✅ Deliverables
- Implemented DTOs, Mappers, and REST Controllers (`BookingController`, `ResourceController`)
- Added `BookingService` with slot validation logic
- Introduced `GlobalExceptionHandler` with `{code, message}` format
- Added Flyway migration `V2__add_booking_time_slot_fk.sql` + `@PrePersist` defaults
- Added Flyway migration `V3__add_idempotency_key_to_booking.sql`
- Implemented Idempotency-Key handling in `POST /bookings` (200/201 logic)

---

## 📝 Technical Notes
- Verified end-to-end flow: Controller → Service → Repository → DB
- Confirmed proper Flyway versioning (V1 → V2 → V3)

---

## ⏭️ Next
- Add `@WebMvcTest` for booking flow (happy + edge paths)
- Generate OpenAPI spec for all endpoints and error responses

---

**Last updated:** 2025-10-21