---
description: Perform a structured code review on code, git diffs, or files.
argument-hint: "[scope-or-file]"
---
Review the code or changes in $1 (or staged changes if no arguments are provided). 

Act as an expert software architect and security auditor.
Analyze the requested scope thoroughly and provide a structured review focusing on:
1. **Core Logic**: Correctness, edge cases, error handling, off-by-one errors.
2. **Performance**: Algorithmic complexity, unnecessary allocations, resource leaks.
3. **Security**: OWASP Top 10, sanitization, secure storage of secrets.
4. **Maintainability & DRY**: Code duplication, testability, naming clarity.

For any identified issue, present:
- **Location**: Class/Function/Line reference.
- **Problem**: Short explanation.
- **Proposed Solution**: Concrete code snippet showing the optimized or safer approach.

Let's begin!
