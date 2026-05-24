# THE CODING SUPERPOWERS APPROACH

You must operate under these core principles to ensure high-quality, precise, and maintainable software development for every task. These guidelines enforce disciplined engineering blockages against "confident junior dev" syndrome.

---

## Principle 1: Think Before Coding
* **Frappe Framework & ERPNext Architecture Check:** For every new project or initialization, you must always ask the user if they want to use the **Frappe Framework** and/or **ERPNext** as the foundational architectural guardlines for the project.
* **No Assumptions:** State your assumptions explicitly. If anything is uncertain or open to multiple interpretations, ask for clarification before guessing. Stop on confusion.

## Principle 2: Simplicity First
* **Docker & Docker Compose Target:** Propose containerization using Docker with Docker Compose, utilizing local directories on the host (bind mounts) for data persistence instead of named docker volumes.
* **Keep it Minimal:** Write the minimum code that solves the exact problem. Avoid premature abstractions or speculative features.

## Principle 3: Surgical Changes
* **Drive-by Guardrail:** Touch only what you must to complete the task. Match existing style and code layouts exactly. No drive-by refactoring or unasked deletions.
* **Dual-Track Documentation Standards:** Always document features thoroughly in separate **User Documentation MD** and **Admin/Technical Documentation MD** files.

## Principle 4: Goal-Driven Execution
* **Autonomous Troubleshooting:** Leverage local Docker engine and Chrome DevTools to resolve defects. Repeat testing/fixing up to a **maximum of 10 retry attempts** before asking the user.
* **Git Worktrees For Precise Comparison:** Use `git worktree add` to spin up a clean branch in a separate workspace, running head-to-head comparison checks simultaneously.
* **Regression logging & Tags:** Commit regression test cases under the `tests/regression/` directory, update the live audit log at `tests/regression/REGRESSION_LOG.md`, and create an associated Git Tag for **every single commit** you make.

## Principle 5: High-Quality UI/UX (UIUX Pro Max Standards)
* **Progressive Loading & Style:** Invoke the `/skill:ui-ux-pro-max` design guidelines whenever tasked on visual interfaces, interactive components, accessibility (WCAG AA), or layout alignments. Do not use emojis as icons.
