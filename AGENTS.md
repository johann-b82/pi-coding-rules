# Project Memory Card (`AGENTS.md`)

This file provides startup onboarding instructions and structural references for the Pi Coding Agent (`pi`).

---

## 📋 Project Overview
* **Name:** `@johann-b82/pi-coding-rules`
* **Description:** Shared AI Coding Agent rules, skills, and prompt templates for teams.
* **Tech Stack:** JSON Settings, Markdowns, Git, Docker, Node.js + Pi Agent.

---

## 🛠 Project Developer Commands

Before initiating tasks, invoke these commands to check, verify, and test codebase behaviors:

| Action | Command | Purpose |
|--------|---------|---------|
| **Validation** | `pi list` | List all discovered packages, prompts, and skills. |
| **Linting** | `npm run lint` (or target framework linter) | Checks syntax and style conformity. |
| **Testing** | `npm test` (or target framework runner) | Runs the automated test and validation suites. |

---

## 🔒 Codebase-Specific Guidelines & Safety Rules
* **Git Commit Workflow:** Every commit made by the agent must be tagged with a corresponding, lightweight Git Tag tracking version/milestone references (e.g., `git tag vX.Y.Z`).
* **Surgical Documentation:** When creating or updating features, document user journeys in a dedicated **User MD** file, and admin operations in a separate **Admin/Tech MD** file.
* **Regression Audit:** Maintain the validation records in `tests/regression/REGRESSION_LOG.md`.
