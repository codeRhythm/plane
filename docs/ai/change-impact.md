# Plane Change Impact

Base: `pull_request`

## Changed Paths

- `.gitattributes`
- `apps/api/plane/api/views/issue.py`
- `apps/api/plane/tests/contract/api/test_issues.py`
- `apps/api/plane/tests/unit/utils/test_paginator.py`
- `apps/api/plane/utils/openapi/__init__.py`
- `apps/api/plane/utils/openapi/parameters.py`
- `apps/api/plane/utils/paginator.py`
- `docs/ai/architecture.md`
- `docs/ai/change-request-template.md`
- `docs/semantic/change_declaration.json`
- `docs/semantic/mappings.json`

## Impact Groups

- `backend`: 6
- `documentation`: 2
- `other`: 1
- `semantic_model`: 2

## Required Follow-ups

- Run backend pytest subset and update backend/domain mappings.
- Run pnpm check or targeted turbo checks and update frontend/package mappings.
- Run .plane-ai-doc-loop/runtime/validate_semantic.py and regenerate derived docs.
