# 6 Functional Requirements

Functional requirements state observable capabilities and remain independent of
a specific product. Use stable IDs of the form `{bb-code}-FR-{number}`, identify
the related KDF, state REQUIRED, RECOMMENDED, or OPTIONAL, and define acceptance
evidence. Never silently delete or reuse a published ID.

The reference requirements below are implemented by `api/openapi.yaml` and
mapped in `api/coverage.yaml`. Replace them for a real BB.

## 6.1 Reference record lifecycle

- **BB-TPL-FR-001** **REQUIRED**: To support `BB-TPL-KDF-001`, an authorised caller MUST be able to retrieve a bounded, cursor-paginated collection of reference records.
- **BB-TPL-FR-002** **REQUIRED**: To support `BB-TPL-KDF-001`, an authorised caller MUST be able to create a record synchronously and retrieve it by its opaque identifier; successful creation MUST identify the created resource.

## 6.2 Long-running work

- **BB-TPL-FR-003** **REQUIRED**: To support `BB-TPL-KDF-002`, an authorised service MUST be able to request an asynchronous record export, poll the returned Operation, and request cancellation.

## 6.3 Components

Describe logical components only when they clarify responsibility or trust
boundaries. Do not require a deployer to reproduce an illustrative component
diagram or a particular internal architecture.
