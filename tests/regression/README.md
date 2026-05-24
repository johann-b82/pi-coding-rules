# Git Worktree Regression Testing & Logging Guide

To ensure zero regressions across new developments, the agent and developers must follow a strict **Dual-Worktree Regression Verification Workflow** and record all test cases and test logs right here in the worktree.

---

## 🌲 Why Git Worktrees?
Using **Git Worktrees** allows you to checkout a clean reference branch (such as `main` or the target release branch) in a completely separate directory alongside your current directory. This enables you to:
1. Compare API payloads, page load speeds, and database schemas directly.
2. Run identical verification scripts on both the current work branch and the pristine master branch simultaneously.
3. Keep your active working directory completely free of dirty checkouts, switching side effects, or target stash/pop issues.

---

## 🚀 The Dual-Worktree Verification Workflow

When development is nearing completion on your feature branch:

1. **Spin up a pristine reference worktree:**
   ```bash
   # From your active repository root:
   git worktree add ../pristine-reference-main main
   ```
2. **Execute regression suites on the pristine reference branch:**
   ```bash
   cd ../pristine-reference-main
   # Compile, run existing tests, check behaviors
   npm test # (or target command)
   ```
3. **Compare and isolate behaviors relative to your active branch:**
   ```bash
   cd - # Return to your feature working directory
   # Compare endpoints or run verification under identical test setups
   ```
4. **Log the test cases and execution outputs:**
   Ensure test results and execution coverage are recorded in `.regression-log` (kept clean in git workspace) or committed to the test log.
5. **Clean up the temporary worktree after verification:**
   ```bash
   git worktree remove ../pristine-reference-main
   ```

---

## 📝 Regression Test Log Template

Whenever a new feature or change is added, append a new test signature to **`tests/regression/REGRESSION_LOG.md`** under the following format:

```markdown
## [YYYY-MM-DD] - Feature Name / Bugfix Label
* **Developer/Agent:** Pi Agent / User Name
* **Active Branch:** `feature/my-new-feature`
* **Pristine Reference Branch:** `main`

### 1. New Regression Test Cases Created
* `test_endpoint_edge_case` - Verifies empty string edge case
* `test_ui_responsive_rendering` - Ensures no Layout Shift (CLS < 0.1) on 375px

### 2. Verification Log (Local Host / Docker Environment)
- [x] Compilation & Typecheck cleanly passing on both directories
- [x] Automated test suites cleanly passing on pristine worktree
- [x] Automated test suites cleanly passing on current feature worktree
- [x] Interactive Chrome DevTools visual analysis verified (if UI)

### 3. Captured Test Logs/Stdout
```
[Paste output console log, Docker container tests result, or pytest run here]
```
```
