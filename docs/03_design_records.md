<!--
TARGET: Developers, architects, technical reviewers.
USAGE: An immutable log of key technical decisions and their rationale. Helps understand the "why" behind the architecture.
-->

# Architectural Design Records (ADR)

This document chronicles the key design decisions made during the development of TerraMind.

---

### ADR-001: Multi-Agent vs. Monolithic Agent

-   **Decision**: We chose a multi-agent architecture with specialized roles.
-   **Rationale**: To increase reliability and maintainability by assigning each agent a single, well-defined responsibility. This allows for simpler prompts and easier debugging.
-   **Date**: YYYY-MM-DD

---

### ADR-002: Introduction of a JSON Plan as an Intermediate Step

-   **Decision**: The `PlannerAgent`'s final output is a structured JSON plan that requires user approval before code generation.
-   **Rationale**: This creates a crucial checkpoint, ensuring user-AI alignment and providing the `CoderAgent` with an unambiguous, structured input, reducing errors.
-   **Date**: YYYY-MM-DD
