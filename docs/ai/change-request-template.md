# Change Request

## Intent

Allow public API clients to paginate project work items with the documented-style
1-based `page` query parameter without repeatedly receiving the first page.

## Affected Domains

- `work_items`

## Contract Changes

- API: `GET /api/v1/workspaces/{slug}/projects/{project_id}/work-items/`
  accepts `page=N` when `cursor` is absent. `cursor` remains canonical and takes
  precedence when both parameters are supplied.
- Database: None.
- Frontend state: None.
- i18n: None.

## Required Evidence

- Source paths: `apps/api/plane/api/views/issue.py`,
  `apps/api/plane/utils/paginator.py`, and
  `apps/api/plane/utils/openapi/parameters.py`.
- Tests: `apps/api/plane/tests/contract/api/test_issues.py` verifies the HTTP
  behavior, while `apps/api/plane/tests/unit/utils/test_paginator.py` verifies
  page conversion, validation, opt-in isolation, and cursor precedence.
- Documentation: `docs/semantic/change_declaration.json`,
  `docs/semantic/mappings.json`, and generated change-impact notes.

## Acceptance Checks

- Targeted API contract test for work-item page pagination.
- `python .plane-ai-doc-loop/runtime/validate_semantic.py --strict-paths --require-baseline --require-generated`
- `python .plane-ai-doc-loop/runtime/check_doc_gate.py --base "origin/preview..."`

## Machine Declaration

Update `docs/semantic/change_declaration.json` with the active domains, mapping IDs, source evidence, and tests for this change.
