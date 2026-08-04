# 7 Data Structures

Describe only information exchanged across the BB boundary. The OpenAPI or
AsyncAPI schema is normative when prose and machine-readable definitions differ.
Include a diagram when relationships cannot be expressed clearly in a table.

## 7.1 Resource model

The template reference model has a `Record`, a paginated `RecordCollection`, and
an `Operation` representing long-running work.

## 7.2 Reference record

| Field | Type | Required | Meaning |
|---|---|---|---|
| `id` | UUID string | Yes in responses | Opaque server-generated record identifier. |
| `name` | string | Yes | Human-readable label without personal data. |
| `status` | enum | Yes | `ACTIVE` or `ARCHIVED`; clients tolerate future values. |
| `createdAt` | RFC 3339 timestamp | Yes in responses | Time at which the record was created. |
| `updatedAt` | RFC 3339 timestamp | Yes in responses | Time of the latest change. |

See [`api/openapi.yaml`](../api/openapi.yaml) for constraints, examples, error
schemas, pagination metadata, and the Operation resource.
