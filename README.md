<!--
TARGET: All visitors (reviewers, new developers, users).
USAGE: Provide a quick, high-level summary of the project and navigation links. Keep it concise.
-->

# CookCodex

**A Methodology for Building with AI, Not Just by AI.**

Author: Jun Xiong (@suredream)

CookCodex is a documentation-first development methodology designed for building complex, maintainable projects in the era of Generative AI. It provides a structured framework that treats documentation not as a chore, but as the central blueprint that guides both human developers and their AI collaborators, ensuring clarity, consistency, and efficient co-creation.

## Why Use CookCodex?

In a traditional workflow, documentation often lags behind code, leading to stale information and ambiguity. When working with AI, this ambiguity is a critical bottleneck. CookCodex solves this by inverting the process.

-   **Reduced Ambiguity:** By defining the 'what' and 'why' before implementation, you create a single source of truth that eliminates guesswork for everyone involved.
-   **Efficient AI Collaboration:** Provide your AI partner with a dedicated, concise, and machine-readable context (`/ai_context`), leading to more accurate and relevant outputs.
-   **Enhanced Maintainability:** A new developer (or you, six months from now) can understand the system's architecture and design rationale without having to reverse-engineer the entire codebase.
-   **Simplified Onboarding:** The `/docs` directory serves as a comprehensive and always-up-to-date guide for new team members.

## The Core Principles

1.  **Docs as the Blueprint:** The `/docs` directory is the canonical source of truth. Code is the *implementation* of this blueprint.
2.  **Separate Contexts for Human & AI:** Humans get rich, narrative detail. AIs get concise, machine-readable summaries. This optimizes collaboration for both.
3.  **Log Decisions, Not Just Code:** The `why` is often more critical than the `how`. Architectural Design Records create an immutable history of your strategic choices.
4.  **AI is a Leveraged Collaborator:** The human is the architect; the AI is the master builder. Use the AI for its strengths while retaining strategic control.

## Project Structure
A project using CookCodex follows this structure:

```
/
├── README.md              # The project's front door and mission statement.
|
├── docs/                    # HUMAN-READABLE: The complete project library.
│   ├── 00_development_guide.md # The rulebook for contributing to this project.
│   ├── 01_tour.md              # A user-focused guide and quick-start.
│   ├── 02_architecture.md      # The "What": The system's complete architecture.
│   ├── 03_design_records.md    # The "Why": A log of key design decisions.
│   └── specs/                  # Detailed specifications for new features.
│   └── cc_prompts/             # Ready-to-use CookCodex prompts
|
├── ai_context/              # AI-READABLE: The "brain food" for your AI collaborator.
│   ├── system_overview.md   # A condensed, machine-friendly architecture summary.
│   └── prompts.md           # A library of prompts and instructions for the AI.
|
└── changelog.md             # A chronological log of all meaningful changes.

....
the rest of the parts will be src, tests, data, models, etc.

```

## The CookCodex Workflow

Development follows a simple, iterative cycle:

1.  **`SPECIFY`**: Define a new feature or change in a new file within `docs/specs/`.
2.  **`DOCUMENT`**: Update the core architecture (`docs/02_architecture.md`), design records (`docs/03_design_records.md`), and the AI's context (`ai_context/`).
3.  **`IMPLEMENT`**: Write the code, either manually or by guiding an AI using the context in `/ai_context`.
4.  **`ITERATE`**: Test the implementation, refine the documentation as needed, and log the final change in `changelog.md`.

## Getting Started: Initialize a Project

You can instantly scaffold a new project with the CookCodex structure using our initialization script. Run the following command in your terminal:

```bash
# Replace the URL with the Raw URL of your Gist
# curl -sSL https://gist.githubusercontent.com/[YOUR_USERNAME]/[YOUR_GIST_ID]/raw/init_cookcodex.sh | bash
```

This will create a new project directory, fully populated with the template files, ready for you to start building.

## The helper prompts you can used

There are a few fundamental prompts in the `docs/cc_prompts` folder that you can fill your

under either `cline` or `roo code`, use @file to apply the followings prompts to your projects.

## Changelog

For a detailed history of changes, see the [**Changelog**](./changelog.md).