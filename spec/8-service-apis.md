# 8 Service APIs

Machine-readable API documents are normative. Keep one canonical entrypoint per
surface and enumerate it in [`api/index.yaml`](../api/index.yaml). The reference
REST contract is [`api/openapi.yaml`](../api/openapi.yaml).

## 8.1 Requirement traceability

Every active REQUIRED or RECOMMENDED interface requirement in Sections 5 and 6
has exactly one disposition in [`api/coverage.yaml`](../api/coverage.yaml).
DRAFT, DEPRECATED, and INAPPLICABLE requirements are not active coverage
obligations. The coverage file is the authoritative requirement-to-interface
mapping.

The template reference maps:

| Requirement | Canonical operations |
|---|---|
| `govstack-bb-template-fr#req-1` | `listRecords` |
| `govstack-bb-template-fr#req-2` | `createRecord`, `getRecord` |
| `govstack-bb-template-fr#req-3` | `requestRecordExport`, `getOperation`, `cancelOperation` |

## 8.2 Contract ownership

- API paths, parameters, schemas, responses, and examples belong in the
  canonical OpenAPI or AsyncAPI file, not copied into Markdown.
- Review `api/coverage.yaml` whenever requirements or operations change.
- Pin shared cross-BB shapes from `api/common/` and record their upstream
  revision in [`api/common/README.md`](../api/common/README.md); keep domain
  schemas in the BB's canonical API document.
