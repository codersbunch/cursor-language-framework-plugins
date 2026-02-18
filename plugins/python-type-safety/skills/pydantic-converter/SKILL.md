---
name: pydantic-converter
description: Convert plain Python dicts, dataclasses, and TypedDicts to Pydantic v2 models with validation, serialization, and JSON schema generation.
---

# Pydantic Converter

## When to use

- Replacing unvalidated dict parameters with typed models
- Adding input validation to API request/response schemas
- Migrating from dataclasses to Pydantic for validation support
- Generating JSON schemas from Python types

## Instructions

1. **Identify conversion targets**:
   - Functions accepting `dict` with known keys
   - TypedDict definitions
   - dataclass definitions
   - Nested dict structures in API handlers

2. **Generate Pydantic v2 model**:
   - Map types to Pydantic field types
   - Add `Field()` with descriptions and constraints
   - Add validators for business rules
   - Add `model_config` for serialization settings

3. **Add validation rules**:
   - String constraints (min_length, max_length, pattern)
   - Numeric constraints (ge, le, gt, lt)
   - Custom validators with `@field_validator`

4. **Update call sites** to use model instead of dict

## Output

```python
from pydantic import BaseModel, Field

class UserCreate(BaseModel):
    name: str = Field(min_length=1, max_length=100)
    email: str = Field(pattern=r'^[^@]+@[^@]+\.[^@]+$')
    age: int = Field(ge=0, le=150)
```
