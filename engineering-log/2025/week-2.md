# Week 02 — 13–21 Oct 2025
**Focus:** Building the REST API layer with consistent error handling and idempotent booking creation.

---

## ✅ Deliverables
- Implemented DTOs, Mappers, and REST Controllers (`BookingController`, `ResourceController`)
- Added `BookingService` with slot validation logic
- Added Flyway migration `V2__add_booking_time_slot_fk.sql` + `@PrePersist` defaults
- Added Flyway migration `V3__add_idempotency_key_to_booking.sql`
- Added `GlobalExceptionHandler` (`{code, message}`) with proper HTTP mapping
- Added Flyway migration `V4__booking_unique_on_active.sql` — unique only for active (`BOOKED`) slots + unique `Idempotency-Key`
- Confirmed 200/201 flow for `POST /bookings` (idempotent behavior)
- Repository method `existsByTimeSlotIdAndStatus()` for conflict detection
- Mapper reads `Booking.startAt/endAt` to avoid lazy-load issues
- 
---

## 🧪 Manual Verification (Postman)

| # | Endpoint | Method | Scenario | Expected |
|---|-----------|---------|-----------|-----------|
| 1 | `/resources` | GET | List all resources | `200 OK` — returns 5 seeded resources |
| 2 | `/resources/{id}/availability?date=YYYY-MM-DD` | GET | Check available slots | `200 OK` — returns free slots array |
| 3 | `/bookings` | POST | Create booking with body `{resourceId, timeSlotId, email}` and header `Idempotency-Key` | `201 Created` — returns new booking |
| 4 | `/bookings` | POST | Repeat same request with same `Idempotency-Key` | `200 OK` — returns existing booking |
| 5 | `/bookings` | POST | Missing `Idempotency-Key` | `400 Bad Request` — `"Idempotency-Key header is required"` |
| 6 | `/bookings` | POST | Slot already booked | `409 Conflict` — `"SLOT_ALREADY_BOOKED"` |
| 7 | `/bookings/{id}` | GET | Fetch existing booking | `200 OK` — returns booking DTO |
| 8 | `/bookings/{invalidId}` | GET | Nonexistent booking | `404 Not Found` — `"Booking not found"` |


## 📝 Technical Notes
- Verified all 4 endpoints in Postman (GET `/resources`, GET `/availability`, POST `/bookings`, GET `/bookings/{id}`)
- Confirmed database-level enforcement via Flyway V4 partial index
- Endpoints return consistent error codes (400, 404, 409, 500)

---

## ⏭️ Next
- Add `@WebMvcTest` for booking flow (happy + edge paths)

---

**Last updated:** 2025-10-24