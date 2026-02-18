---
name: run-mypy
description: Run mypy in strict mode across the codebase and generate a type error report with suggested fixes.
---

# Run Mypy

Run mypy strict type checking and generate actionable report.

## Steps

1. Run `mypy --strict src/` with configured settings
2. Parse output and group errors by file
3. Categorize errors by type (missing annotation, incompatible types, etc.)
4. Suggest fixes for common error patterns
5. Show progress: errors this run vs. previous run
6. Output report to `mypy-report.md`
7. Fail CI if error count increases from baseline
