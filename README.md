# GovStack Building Block Template

This repository is the starting point for a GovStack Building Block (BB)
specification. Replace the generic reference domain with the BB's real
requirements while preserving its traceability and conformance structure.

## Start a BB specification

1. Give every normative requirement a stable identifier based on the BB code,
   such as `REGISTRY-FR-001`. Never reuse an identifier for a different
   requirement.
2. Replace the reference contract at `api/openapi.yaml`. Keep `api/index.yaml`
   as the canonical API registry. Keep the shared files under `api/common/`
   pinned to their recorded upstream version and revision.
3. Map every normative interface requirement in `api/coverage.yaml`.
4. Run the checks in `test/plan.md` before requesting specification review.

The reference API is intentionally small. It demonstrates synchronous creation,
pagination, long-running operations, standard errors, trace context, and OAuth
2.0 without prescribing a domain model for real BBs.

## Repository structure

```text
spec/                    GitBook specification and stable requirements
api/index.yaml           registry of canonical API documents
api/openapi.yaml         canonical OpenAPI 3.1 reference contract
api/coverage.yaml        authoritative requirement-to-interface mapping
api/common/              pinned, vendored cross-BB contract components
api-design-guide/        cross-BB API design rules and lint tooling
test/plan.md             specification and implementation conformance plan
examples/                deployable implementation examples
```

Pushes to `main` publish the GitBook content under `spec/`. The API contract in
`api/` remains the machine-readable source of truth for operations and schemas.

## ORB setup

Documentation for ORB setup is available here:
[ORB setup instruction](https://govstack-global.atlassian.net/wiki/spaces/GH/pages/191692823/ORB+setup+instruction)
