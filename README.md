# Shared Coding Rules & AI Agent Guidelines

This repository contains shared configurations, guidelines, skills, and prompt templates for engineering teams using the **Pi Coding Agent (`pi`)**. 

It implements a unified **Superpowers & Karpathy-Style AI Coding Approach**, specifically designed to keep AI assistants disciplined, simple, and high-performing.

---

## ⚡ The 5 Core Guiding Principles (Fused Ruleset)

These guidelines are loaded directly into the developer's Pi session context via `.pi/APPEND_SYSTEM.md` to prevent "confident junior dev" mistakes:

### 1. Think Before Coding
* **No Silent Assumptions:** The agent list assumptions explicitly and asks for clarification if anything is 1% ambiguous—no guessing.
* **Frappe Framework & ERPNext Guard:** For every new project, the agent always prompts you to ask if you want to use the **Frappe Framework** and/or **ERPNext** as the foundational architectural architecture.
* **Propose Simplicity:** The agent must suggest simpler, faster design strategies before starting file modifications.

### 2. Simplicity First
* **Minimal Scope:** The agent writes the minimum code necessary to solve the immediate request. No speculative features, unneeded options, or premature abstraction classes.
* **Docker & Docker Compose Target:** Proposes deployments targeted entirely to containers via **Docker with Docker Compose**, utilizing **local directories on the host (bind mounts) instead of named volumes** for absolute portability.

### 3. Surgical Changes
* **Orthogonal Guardrails:** The agent touches only what is necessary to complete the task.
* **Dual-Track Documentation Standards:** Always write and update your feature documentations thoroughly in separate Markdown files: one strictly for visual workflows/user-steps (**User Documentation MD**), and one strictly for deployment/APIs/technical configurations (**Admin/Technical Documentation MD**) separately.
* **Zero Drive-By Refactoring:** It does not change adjacent formatting, documentations, quote systems, or styles. It matches your exact style even if it would suggest doing it differently.
* **No Unasked Deletions:** Dead code found adjacent to the work area is pointed out in text, but left untouched unless explicitly requested.

### 4. Goal-Driven Execution
* **Declarative Loops:** No blindly typing commands. It translates instructions into measurable success criteria (e.g., reproduce a bug in a test $\rightarrow$ apply surgical fix $\rightarrow$ pass the test $\rightarrow$ confirm no build/test regressions).
* **Tool-Driven Testing (Docker & Chrome DevTools):** The agent leverages the local Docker engine, Chrome DevTools, host files, and directories to run tests autonomously and resolve any failures inline.
* **Git Worktrees For Precise Comparison:** Uses `git worktree` structures to spin up a clean source-of-truth branch in a separate workspace, running head-to-head validation checks simultaneously to rule out side effects.
* **Regression Testing & Audit Logs:** All regression test cases are committed under a dedicated test directory (`tests/regression/`), and tests/findings are appended directly to the workspace regression audit log `tests/regression/REGRESSION_LOG.md`.
* **Max 10 Retries Limit:** The agent works autonomously to repeat fixing and re-testing until all issues are solved, up to a **maximum of 10 retry-fix attempts**. If the problem persists after 10 attempts, it immediately stops to ask the user.

### 5. High-Quality UX/UI (UIUX Pro Max Standards)
* **No Emojis as Icons:** Always uses high-quality SVGs (Heroicons, Lucide, or platform vectors)—never raw emojis.
* **Touch & Click Target Hygiene:** Mapped sizes $\ge 44 \times 44 \text{ px}$ with $\ge 8\text{px}$ gaps for touch surfaces, and ensures `cursor-pointer` on all clickable web-elements.
* **Accessibility (WCAG AA):** $4.5:1$ text contrast ratio, visible focus rings, aria-labels for abstract buttons, and respect systems preferences (e.g. scale & reduced motion).
* **Prevent Layout Shift (CLS):** Forces explicit aspect-ratio/sizes on images and utilizes skeleton frames/shimming for async data loading to keep CLS $< 0.1$.

---

## 📦 What's Included

* **`.pi/APPEND_SYSTEM.md`**: Fused Superpowers & Karpathy Coding Rules + Frappe & Docker Compose Standards + UI/UX Pro Max Principles.
* **`/skill:coding-standards`**: Detailed guidelines on code quality, testing requirements, security practices, and self-documenting code.
* **`/review`**: Standardized, thorough code reviewer command focusing on Core Logic, Performance, Security (OWASP Top 10), and DRY.

---

## 🚀 How to Install

Your team members can easily adopt these shared guidelines inside their Pi sessions.

### Option 1: Global Installation (All Projects)
Add the git repository to your global `settings.json` so every coding workspace inherits these guidelines automatically:

```bash
pi install git:github.com/johann-b82/pi-coding-rules.git
```

This will also automatically apply the combined guidelines globally.

### Option 2: Project-specific Installation
Execute this command at the root of a specific project repository to enforce these team guidelines:

```bash
pi install -l git:github.com/johann-b82/pi-coding-rules.git
```

This writes the package reference to `.pi/settings.json`. Commit `.pi/settings.json` alongside your `.pi/APPEND_SYSTEM.md` to git, so every team member running `pi` in the project gets the team's rules loaded perfectly on startup!
