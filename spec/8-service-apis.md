# 8 Service APIs

Machine-readable API documents are normative. Keep one canonical entrypoint per
surface and enumerate it in [`api/index.yaml`](../api/index.yaml). The reference
REST contract is [`api/openapi.yaml`](../api/openapi.yaml).

## 8.1 Requirement traceability

Every normative interface requirement in Sections 5 and 6 has exactly one
disposition in [`api/coverage.yaml`](../api/coverage.yaml). The coverage file is
the single authoritative requirement-to-interface mapping. A BB records a
planned, external-standard, or non-applicable interface explicitly rather than
silently omitting it.

The template reference maps:

| Requirement | Canonical operations |
|---|---|
| `BB-TPL-FR-001` | `listRecords` |
| `BB-TPL-FR-002` | `createRecord`, `getRecord` |
| `BB-TPL-FR-003` | `requestRecordExport`, `getOperation`, `cancelOperation` |
| `BB-TPL-XR-001` | `getHealth` |
| `BB-TPL-XR-002` | All reference operations through schema and guide validation |
| `BB-TPL-XR-003` | All non-health operations |

## 8.2 Contract ownership

- API paths, parameters, schemas, responses, and examples belong in the
  canonical OpenAPI or AsyncAPI file, not copied into Markdown.
- Review `api/coverage.yaml` whenever requirements or operations change.
- Pin shared cross-BB shapes from `api/common/` and record their upstream
  revision in [`api/common/README.md`](../api/common/README.md); keep domain
  schemas in the BB's canonical API document.
