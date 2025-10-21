# ADR 003 — REST Design Plan

**Status:** Accepted (self-reviewed)  
**Date:** 2025-10-13
**Updated:** 2025-10-21

## Context
After finishing the entities, DTOs, and mappers, I needed to decide how the REST API should be structured.  
For now, only the API contract is defined — no controllers or endpoints yet.  
The goal was to keep the design clear and aligned with the current domain model.

## Decision
- Three main API resources: `resources`, `availability`, and `bookings`.
- REST endpoints implemented according to `api-contract.mmd`.
- Unified error format `{code, message}` via `GlobalExceptionHandler`.
- Added idempotent booking creation using the `Idempotency-Key` header.

## Consequences
**Pluses:** 
- Clear direction for API layer. 
- DTOs and mappers aligned with the contract.  
- Added idempotent booking creation using the `Idempotency-Key` header.

**Minuses:** 
- Test coverage for edge cases (`@WebMvcTest`) still pending.
- OpenAPI specification not yet generated.
- 
## Links
- [API Contract](../designs/api-contract.mmd)
- [Milestone M00 — Foundations](../milestones/m00-foundations.md)
