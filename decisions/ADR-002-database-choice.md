# ADR 002 — Database: PostgreSQL + Flyway

**Status:** Accepted (self-reviewed)  
**Date:** 2025-10-09  
**Updated:** 2025-10-10

## Context
Coworkly needs a relational database for rooms, timeslots, and bookings.  
It must support relations (1-n, n-n) and allow versioned schema changes.

## Decision
- Use PostgreSQL for the main database.
- Run it locally via Docker Compose.
- Manage schema changes with **Flyway** migrations (active from V1__init.sql).
- Use **Spring profiles** (`dev`, `no-db`) for flexible startup modes.

## Consequences
**Pluses:** reliable SQL engine, easy Docker setup, version-controlled schema and repeatable migrations via Flyway.  
**Minuses:**  Flyway adds extra migration discipline.

## Alternatives considered
1. **H2** — only for tests, not persistent.

## Links
- [ERD — Booking Model](../designs/erd-booking.mmd)
- [Migration V1__init.sql](../src/main/resources/db/migration/V1__init.sql)
- [Milestone M00 — Foundations](../milestones/m00-foundations.md)
