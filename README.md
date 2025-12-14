# Agent Instructions Docs

## Table of Contents

- [What This Is](#what-this-is)
- [How To Use It](#how-to-use-it)
- [Repository Structure](#repository-structure)
- [Core Files](#core-files)
  - [AGENTS.md](#agentsmd)
  - [documentation/agentic-guidelines/](#documentationagentic-guidelines)
- [How It Works](#how-it-works)
- [Why This Matters](#why-this-matters)

## What This Is

AI agents can make better decisions when they have access to well-defined rules and conventions. Instead of embedding all rules directly into agent prompts (which can be costly in terms of tokens), we keep them in **separate guideline files** that agents can load _only when relevant to a specific task_. This approach improves efficiency and reduces unnecessary token usage while maintaining consistent behavior across different agents and projects.

## How To Use It

- Create a new repository from this Template.
- Keep `documentation/` & `AGENTS.md` in the repository root and set-up the rest of your process as usual.

OR

- Download the repository .zip-file
- copy the `documentation/`-folder and `AGENTS.md`-file inside the root of your project

If you prefer certain `.md`-files only, feel free to click download them individually:

### Naming Guidelines

- [Types & Interfaces](documentation/agentic-guidelines/code-quality-guidelines/naming-guidelines/type-interface-naming-guidelines.md)
- [Components, Functions, Variables](documentation/agentic-guidelines/code-quality-guidelines/naming-guidelines/components-function-variable-naming-guidelines.md)
- [Files & Folders](documentation/agentic-guidelines/code-quality-guidelines/naming-guidelines/file-folder-naming-guidelines.md)

### Other Guidelines

- [Types](documentation/agentic-guidelines/code-quality-guidelines/types-guidelines.md)

- [Commit Message](documentation/agentic-guidelines/commit-pull-request-guidelines/commit-guidelines.md)

- [Pull Request](documentation/agentic-guidelines/commit-pull-request-guidelines/pull-request-guidelines.md)

### Documentation Guidelines

- [Documentation Standards](documentation/agentic-guidelines/documentation-guidelines/documentation-standards-guidelines.md)

## Repository Structure

```plaintext
├── AGENTS.md
├── README.md
├── .gitignore
├── todos.md
└── documentation/
    └── agentic-guidelines/
        ├── code-quality-guidelines/
        │   ├── naming-guidelines/
        │   │   ├── components-function-variable-naming-guidelines.md
        │   │   ├── file-folder-naming-guidelines.md
        │   │   └── type-interface-naming-guidelines.md
        │   └── types-guidelines.md
        ├── commit-pull-request-guidelines/
        │   ├── commit-guidelines.md
        │   └── pull-request-guidelines.md
        └── documentation-guidelines/
            └── documentation-standards-guidelines.md
```

## Core Files

### `AGENTS.md`

This is the **baseline rule set** for all AI agents. It should live in the **project root** alongside `documentation/`. It contains only the most essential principles that apply on every agent invocation (e.g., avoid hallucinations, ask for clarification when context is missing, prefer project files over assumptions). Keep this file small to minimize token usage.

### `documentation/agentic-guidelines/`

This folder contains **topic-specific guideline files**, organized into small, task-focused subfolders. These files define naming conventions, commit message rules, pull request expectations, and documentation standards. Agents should _only load the guideline file(s) relevant to the current task_. For example:

- When generating a commit message, the agent should read `commit-guidelines.md`.
- When naming a new component or type, the agent should read `naming-conventions-guidelines.md`.

By loading only the necessary files, agents avoid reading irrelevant content and keep token costs low.

## How It Works

1. **Baseline Rules in AGENTS.md**  
   Every agent invocation should start with the rules from `AGENTS.md`. These rules govern basic agent behavior and high-level expectations.

2. **Task-Triggered Guidelines**  
   When a specific task requires additional knowledge (e.g., formatting commit messages, naming conventions), the agent should load only the relevant guideline file from `documentation/agentic-guidelines/`.

3. **Documentation Maintenance**  
   The guidelines in this repository should be kept up to date with project conventions. If conventions change (e.g. naming styles, folder structure recommendations), update the relevant guideline file.

## Why This Matters

Embedding all rules directly into agent prompts leads to:

- larger prompt sizes
- increased token usage and cost
- slower agent execution

By separating baseline rules and specific guidelines, this repo enables:

- **modular, task-specific context loading**
- **better token efficiency**
- **clearer rule management**
- **reusable agent behavior across projects**

---

---

## Quick Access (Guideline Shortcuts)

Here are direct links to common guideline files for easier navigation:

### Naming Guidelines

- [Types & Interfaces](documentation/agentic-guidelines/code-quality-guidelines/naming-guidelines/type-interface-naming-guidelines.md)
- [Components, Functions, Variables](documentation/agentic-guidelines/code-quality-guidelines/naming-guidelines/components-function-variable-naming-guidelines.md)
- [Files & Folders](documentation/agentic-guidelines/code-quality-guidelines/naming-guidelines/file-folder-naming-guidelines.md)

### Other Guidelines

- [Types](documentation/agentic-guidelines/code-quality-guidelines/types-guidelines.md)

- [Commit Message](documentation/agentic-guidelines/commit-pull-request-guidelines/commit-guidelines.md)

- [Pull Request](documentation/agentic-guidelines/commit-pull-request-guidelines/pull-request-guidelines.md)

### Documentation Guidelines

- [Documentation Standards](documentation/agentic-guidelines/documentation-guidelines/documentation-standards-guidelines.md)

---

## License

This project is licensed under the **MIT License**. See the `LICENSE` file for details.
