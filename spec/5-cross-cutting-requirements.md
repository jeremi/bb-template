# 5 Cross-Cutting Requirements

List requirements that apply across functional areas. Use
`{bb-code}-XR-{number}` IDs, RFC 2119 language, and a verification method.

## 5.1 Requirements

- **BB-TPL-XR-001** **REQUIRED**: The BB MUST expose the unauthenticated `/health` contract defined in the canonical OpenAPI document without returning internal system detail.
- **BB-TPL-XR-002** **REQUIRED**: The canonical API documents MUST pass their base schema validators and the GovStack API Design Guide ruleset targeted by the documents.
- **BB-TPL-XR-003** **REQUIRED**: Non-operational operations MUST declare OAuth 2.0 security and W3C Trace Context as defined by the canonical API contract.

## 5.2 Exceptions to architectural cross-cutting requirements

State each exception, its rationale, approver, and expiry or review date. The
template declares no exceptions.

## 5.3 Standards

- [OpenAPI 3.1](https://spec.openapis.org/oas/v3.1.0) for synchronous HTTP APIs.
- [RFC 9457](https://www.rfc-editor.org/rfc/rfc9457) for HTTP problem details.
- [OAuth 2.0](https://www.rfc-editor.org/rfc/rfc6749) for authorised API access.
- [W3C Trace Context](https://www.w3.org/TR/trace-context/) for distributed tracing.
- The [GovStack Cross-BB API Design Guide](../api-design-guide/README.md) for cross-BB conventions.
