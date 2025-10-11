# ADR 002 — Database: PostgreSQL + Flyway

**Status:** Accepted (self-reviewed)  
**Date:** 2025-10-09  
**Updated:** 2025-10-11

## Context
Coworkly needs a relational database for rooms, timeslots, and bookings.  
It must support relations (1-n, n-n) and allow versioned schema changes.
Initial schema design and migration (`V1__init.sql`) were verified through repository tests.Confirmed persistence via `BookingRepositoryTest` (@DataJpaTest) — Flyway and JPA mapping validated.

## Decision
- Use PostgreSQL for the main database.
- Run it locally via Docker Compose.
- Manage schema changes with **Flyway** migrations (active from V1__init.sql).
- Use **Spring profiles** (`dev`, `no-db`) for flexible startup modes.
- Confirmed persistence via `BookingRepositoryTest` (@DataJpaTest) — Flyway and JPA mapping validated.

## Consequences
**Pluses:** reliable SQL engine, easy Docker setup, version-controlled schema and repeatable migrations via Flyway; verified through integration test.   
**Minuses:**  Flyway adds extra migration discipline.

## Alternatives considered
1. **H2** — only for tests, not persistent.

## Links
- [ERD — Booking Model](../designs/erd-booking.mmd)
- [Migration V1__init.sql](https://github.com/KasiaKab/coworkly-api/blob/dev/src/main/resources/db/migration/V1__init.sql)
- [BookingRepositoryTest.java](https://github.com/KasiaKab/coworkly-api/blob/dev/src/test/java/com/coworkly/repository/BookingRepositoryTest.java)
- [Milestone M00 — Foundations](../milestones/m00-foundations.md)
