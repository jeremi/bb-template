# Building Block conformance test plan

This plan covers the specification and externally observable implementation
contract. A BB may add domain and deployment tests, but must not remove checks
for its REQUIRED requirements.

## 1. Specification checks

1. Validate every document listed in `api/index.yaml` with its base schema
   validator.
2. Run `node api-design-guide/linter/cli.mjs --repo-root . --fail-on error`
   (install the base validators first; see
   `api-design-guide/guides/validating-your-spec.md`).
3. Confirm every normative requirement ID is unique and has exactly one valid
   disposition in `api/coverage.yaml`.
4. Confirm every `operation` disposition names existing, unique `operationId`
   values.
5. Resolve every local `$ref` without network access.

## 2. Reference contract tests

| Requirement | Test |
|---|---|
| `BB-TPL-FR-001` | List records with no cursor, follow `nextCursor`, enforce the `pageSize` maximum, and treat the integrity-protected cursor as opaque. |
| `BB-TPL-FR-002` | Create with a new `Idempotency-Key`, verify `201` and `Location`, retrieve the record, then replay the same request and receive the original result. |
| `BB-TPL-FR-003` | Request an export, verify `202` and Operation `Location`, poll to a terminal status, and exercise cancellation. |
| `BB-TPL-XR-001` | Call `/health` without credentials and verify `application/health+json` without internal details. |
| `BB-TPL-XR-003` | Reject missing or insufficient OAuth access tokens, propagate `traceparent`, and make an error `traceId` equal the effective W3C trace-id. |

## 3. Error and resilience tests

- Verify every documented 4xx and 5xx response uses
  `application/problem+json`, has the RFC 9457 fields plus `code`, `traceId`,
  and `timestamp`, and declares `Cache-Control: no-store`.
- Verify malformed input produces field-level JSON Pointer errors.
- Verify a reused idempotency key with a different body is rejected.
- Verify no credentials or personal data appear in URLs or logs collected as
  test evidence.

## 4. Integration and deployment evidence

Record the implementation version, test environment, commands, timestamps, and
result artifacts. Where the BB communicates through an interoperability
mediator or adaptor, run the same contract suite through that boundary. A
release is conformant only when all REQUIRED requirement tests pass and no
undeclared interface exception remains.
