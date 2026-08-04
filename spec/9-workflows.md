# 9 Internal Workflows

Describe externally observable sequences needed to understand a requirement.
Internal implementation steps are informative unless a requirement makes them
observable. Name the requirement IDs exercised by each workflow.

## 9.1 Create and retrieve a record

Requirement: `BB-TPL-FR-002`.

```mermaid
sequenceDiagram
    participant Client
    participant BB
    Client->>BB: POST /v1/records with OAuth and Idempotency-Key
    BB-->>Client: 201 Created with Location
    Client->>BB: GET Location
    BB-->>Client: 200 Record
```

## 9.2 Request long-running work

Requirement: `BB-TPL-FR-003`.

```mermaid
sequenceDiagram
    participant Service
    participant BB
    Service->>BB: POST /v1/exports with client credentials
    BB-->>Service: 202 Accepted with Operation Location
    loop Until terminal status
        Service->>BB: GET Operation Location
        BB-->>Service: 200 Operation
    end
```
