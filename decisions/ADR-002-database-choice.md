# ADR 002 — Database: PostgreSQL + Flyway

**Status:** Accepted (self-reviewed)  
**Date:** 2025-10-09

## Context
Coworkly needs a relational database for rooms, timeslots, and bookings.  
It must support relations (1-n, n-n) and allow versioned schema changes.

## Decision
- Use PostgreSQL for the main database.
- Run it locally via Docker Compose.
- Use Flyway for migrations (temporarily disabled — PG 16.10 not yet supported).

## Consequences
**Pluses:** reliable SQL engine, easy Docker setup, version-controlled schema.  
**Minuses:**  Flyway disabled until version update; manual migration discipline required.

## Alternatives considered
1. **H2** — only for tests, not persistent.

## Links
- [ERD — Booking Model](../designs/erd-booking.mmd)
- [Migration V1__init.sql](../src/main/resources/db/migration/V1__init.sql)
- [Milestone M00 — Foundations](../milestones/m00-foundations.md)
