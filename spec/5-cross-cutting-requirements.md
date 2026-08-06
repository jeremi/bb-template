# 5 Cross-Cutting Requirements

Every GovStack Building Block inherits `govstack-cfr`. Do not repeat inherited
requirements here. Define a Building Block cross-functional requirement only
when this specification extends or replaces a parent requirement, and state the
parent relationship explicitly.

## 5.1 Requirements

The template defines no additional cross-functional requirements. A real BB
adds one in the same format as Section 6, using a canonical
`govstack-bb-{name}-cfr#req-{number}` identifier and an `extends` or `replaces`
relationship to the applicable `govstack-cfr-*#req-{number}` parent.

## 5.2 Parent requirement relationships

An inherited IMMUTABLE requirement cannot be changed. An EXTENSIBLE requirement
may be tightened, and a REPLACEABLE requirement may be replaced while
preserving its external contract. Use INAPPLICABLE only where the GovStack
Requirements Model permits it and include the rationale in the requirement.

## 5.3 Standards

- [OpenAPI 3.1](https://spec.openapis.org/oas/v3.1.0) for synchronous HTTP APIs.
- [RFC 9457](https://www.rfc-editor.org/rfc/rfc9457) for HTTP problem details.
- [OAuth 2.0](https://www.rfc-editor.org/rfc/rfc6749) for authorised API access.
- [W3C Trace Context](https://www.w3.org/TR/trace-context/) for distributed tracing.
- The [GovStack Cross-BB API Design Guide](../api-design-guide/README.md) for cross-BB conventions.
