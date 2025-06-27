<!--
TARGET: Developers, architects.
USAGE: The single source of truth for the system's structure, components, and data flows.
-->

# System Architecture

This document describes the technical architecture of the TerraMind AI Co-Pilot.

## High-Level Diagram

*(Insert your architecture diagram here, showing agents and data flow, e.g., using Mermaid or a PNG image.)*

## Agent Profiles

### 1. RootAgent (Orchestrator)
-   **Role**: The main coordinator that directs user queries through a fixed workflow.
-   **Model**: `gemini-2.5-pro`

### 2. GuardAgent
-   **Role**: Acts as a gatekeeper to validate all incoming queries for scope (F1) and capability (F6).
-   **Model**: `gemini-1.5-flash-latest`

### 3. PlannerAgent
-   **Role**: Collaborates with the user via dialogue to create a detailed JSON analysis plan.
-   **Model**: `gemini-2.5-pro`

### 4. CoderAgent
-   **Role**: Takes the final JSON plan and generates executable Google Earth Engine code and a cost estimate.
-   **Model**: `gemini-2.5-pro`
