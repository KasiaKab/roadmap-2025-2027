# ADR 003 — REST Design Plan

**Status:** Accepted (self-reviewed)  
**Date:** 2025-10-13

## Context
After finishing the entities, DTOs, and mappers, I needed to decide how the REST API should be structured.  
For now, only the API contract is defined — no controllers or endpoints yet.  
The goal was to keep the design clear and aligned with the current domain model.

## Decision
- Define three main resources in the API: `resources`, `availability`, and `bookings`.
- Describe their relations and expected operations in `api-contract.mmd`.
- Keep the structure minimal and focused on the MVP scope (list, get, create).
- Implementation of controllers will follow this contract later.

## Consequences
**Pluses:** clear direction for API layer; DTOs and mappers aligned with the contract.  
**Minuses:** endpoints and handlers still missing — implementation needed in next steps.

## Links
- [API Contract](../designs/api-contract.mmd)
- [Milestone M00 — Foundations](../milestones/m00-foundations.md)
