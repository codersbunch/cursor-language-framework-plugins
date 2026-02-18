---
name: type-annotator
description: Auto-add type annotations to Python functions, classes, and variables. Infers types from usage and docstrings.
---

# Type Annotator

## When to use

- Adding types to legacy untyped Python code
- After writing new functions without annotations
- Before enabling mypy strict mode on a codebase

## Instructions

1. **Analyze function signatures** - infer parameter types from:
   - How parameters are used in the function body
   - Docstring type descriptions
   - Call sites in the codebase
   - Default values

2. **Infer return types** from:
   - Return statements
   - Docstring Returns section
   - Type of values assigned to result

3. **Annotate variables** where type is not obvious from assignment

4. **Upgrade bare types**:
   - `dict` → `dict[str, Any]`
   - `list` → `list[SpecificType]`
   - `Optional` → `X | None` (Python 3.10+)

5. **Suggest Pydantic models** for dict parameters with known structure

6. **Run mypy** after annotation and fix any errors

## Output

- Annotated file with all type hints added
- List of types that could not be inferred (need manual review)
- mypy output after annotation
