# ADR 0001 — Monolith-First Architecture

**Status:** Accepted  
**Date:** 2025-10-08

## Context
To start Coworkly I had to decide if I build one app or split it into services.  
It’s my first full backend after a Java course, so I want to keep things simple and working.  
Goal: build a clean, working API and learn how all parts connect.

## Decision
I use **Spring Boot** as a single monolithic app.  
It lets me build fast, with one codebase, one DB, and clear structure.  
Later (M2–M3) I can split modules if needed.

## Consequences
**Pluses:** easy to run, test, and deploy; one project to focus on.  
**Minuses:** less flexible for scaling later.  

## Alternatives considered
1. **Microservices** — too complex for one person and early stage.
2. **Multiple small apps** — not needed until real traffic or scaling.

## Links
- `designs/C4-context.mmd`
- `designs/C4-container.mmd`
- `milestones/m00-foundations.md`
- `Coworkly - overview.pdf`
