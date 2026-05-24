# Shared Coding Rules & Templates

This repository contains shared configurations, skills, and prompt templates for teams using the **Pi Coding Agent (`pi`)**.

## 📦 What's Included

* **`/skill:coding-standards`**: Guidelines on code quality, testing requirements, security best practices, and documentation.
* **`/review`**: Standardised, thorough code reviewer command that audits correctness, performance, security, and DRY principles.

---

## 🚀 How to Install

Your team members can easily install these shared rules directly inside their Pi agent.

### Option 1: Global Installation (All Projects)
Add the git repository to the global `settings.json`:

```bash
pi install git:github.com/johann-b82/pi-coding-rules.git
```

### Option 2: Project-specific Installation
If you only want this applied to a specific project repository, run this command in the root of your project directory:

```bash
pi install -l git:github.com/johann-b82/pi-coding-rules.git
```
This adds the package to `.pi/settings.json`, which you can commit to your project git repository so that any team member has these rules loaded automatically.

---

## 🛠 Usage

1. Type `/review` in the Pi prompt to run the structured review command.
2. The agent automatically has access to `/skill:coding-standards` to answer any questions inline with formatting, testing, and security guides.
# pi-coding-rules
