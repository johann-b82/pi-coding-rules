---
name: coding-standards
description: Enforces team coding standards, architecture rules, testing practices, and styling conventions.
---

# Code Review and Architecture Standards

Use this skill when developing, refactoring, or reviewing code to ensure high standards of readability, security, and maintainability.

## 1. Coding Style & Quality
* **Readability First**: Code must be expressive and self-documenting. Use descriptive variable/function names.
* **Pure Functions**: Favor functional programming concepts: isolate side effects and avoid global state mutation.
* **Formatting**: Ensure your codebase formatting conventions are strictly applied (e.g., Prettier/ESLint configs when working in JS/TS).

## 2. Documentation & Comments
* Do not restate *what* the code does in inline comments. Document *why* it does it.
* Document non-trivial algorithms, workarounds for external bugs, and legacy constraints.
* Maintain clear `README.md` and keep public API documentations updated.

## 3. Testing Requirements
* Everything must be testable. If mock-writing is difficult, refactor into smaller, decoupled functions.
* Every feature change or bugfix should include corresponding unit or integration tests.
* Ensure code coverage does not decrease.

## 4. Security Practices
* Never hardcode API keys, secrets, private keys, or credentials. Use environment configuration.
* Sanitize all inputs to prevent injection and scripting attacks.
* Minimize dependencies and regularly audit them for vulnerabilities.
