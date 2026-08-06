# 6 Functional Requirements

Functional requirements state observable capabilities and remain independent of
a specific product. Follow the GovStack Requirements Model: give every
requirement a canonical `govstack-bb-{name}-fr#req-{number}` identifier and
exactly one level, mutability, and observability classifier. Never silently
delete or reuse a published requirement number.

The reference requirements below are implemented by `api/openapi.yaml` and
mapped in `api/coverage.yaml`. Replace them for a real BB.

## 6.1 Reference record lifecycle

### #1 Retrieve reference records (REQUIRED EXTENSIBLE OBSERVABLE)

`govstack-bb-template-fr#req-1`

KF: Manage reference records

An authorised caller can retrieve a bounded, cursor-paginated collection of
reference records.

### #2 Create and retrieve a reference record (REQUIRED EXTENSIBLE OBSERVABLE)

`govstack-bb-template-fr#req-2`

KF: Manage reference records

An authorised caller can create a record synchronously and retrieve it by its
opaque identifier. Successful creation identifies the created resource.

## 6.2 Long-running work

### #3 Request and observe a record export (REQUIRED EXTENSIBLE OBSERVABLE)

`govstack-bb-template-fr#req-3`

KF: Run long-running work

An authorised service can request an asynchronous record export, poll the
returned Operation, and request cancellation.

## 6.3 Components

Describe logical components only when they clarify responsibility or trust
boundaries. Do not require a deployer to reproduce an illustrative component
diagram or a particular internal architecture.
