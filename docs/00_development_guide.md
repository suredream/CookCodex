<!--
TARGET: Developers and contributors.
USAGE: This is the rulebook for maintaining the project's documentation and code. It ensures consistency and quality.
-->

# Development Guide

Welcome, developer! This guide outlines the documentation structure and the workflow for maintaining and extending this project, following the **CookCodex** methodology. Adhering to this guide is crucial for efficient collaboration, both with human teammates and our GenAI co-pilot.

## Documentation Philosophy

Our documentation follows two core principles:

1.  **Single Source of Truth**: Every piece of information has one and only one canonical location. Other documents should link to it, not copy it.
2.  **Human-Readable vs. AI-Context**: We maintain separate documentation for human deep-reading (`/docs`) and for providing concise context to the AI (`/ai_context`).

## Directory Structure Overview

-   `README.md`: The public-facing entry point.
-   `/docs`: The library for human understanding.
    -   `00_development_guide.md`: This very file. The project's "how-to".
    -   `01_tour.md`: A user-focused walkthrough.
    -   `02_architecture.md`: The definitive description of *what* the system is.
    -   `03_design_records.md`: The definitive history of *why* the system is designed this way.
    -   `specs/`: Detailed plans for new or existing features.
-   `/ai_context`: The "brain food" for our GenAI partner. This is the primary interface for AI-assisted development.
-   `changelog.md`: A running log of all significant changes.

## The Development Workflow: How to Make a Change

Whether fixing a bug or adding a feature, follow these steps:

1.  **Plan in `docs/specs` (for new features)**: Create a new spec file to outline the goal, impact, and design of the new feature.
2.  **Update Design Records**: If the change involves a significant choice, add an entry to `docs/03_design_records.md`.
3.  **Update the Architecture**: Modify `docs/02_architecture.md` (for humans) and `ai_context/system_overview.md` (for AI) to reflect any structural changes.
4.  **Update the Prompts**: If an agent's behavior is changing, update its prompt in `ai_context/prompts.md`. This is the single source of truth for agent instructions.
5.  **Write the Code**: With all documentation updated, you (or the AI with your guidance) can now implement the code changes. The AI should be pointed to the `/ai_context` directory for its required context.
6.  **Update User-Facing Docs**: Update `docs/01_tour.md` or `README.md` if the change affects the user experience.
7.  **Log the Change**: Add a concise entry to `changelog.md`.

By following this "documentation-first" approach, we ensure our project remains clear, maintainable, and easy to collaborate on.
