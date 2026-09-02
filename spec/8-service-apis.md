# 8 Service APIs

This section provides a reference for APIs that should be implemented by this Building Block. The APIs defined here establish a blueprint for how the Building Block will interact with other Building Blocks. Additional APIs may be implemented by the Building Block, but the listed APIs define a minimal set of functionality that should be provided by any implementation of this Building Block.&#x20;

The [GovStack non-functional requirements document](https://govstack.gitbook.io/specification/architecture-and-nonfunctional-requirements/6-onboarding) provides additional information on how 'adaptors' may be used to translate an existing API to the patterns described here. This section also provides guidance on how candidate products are tested and how GovStack validates a product's API against the API specifications defined here.&#x20;

{% hint style="success" %}
Keep the canonical interface inventory in [`api/index.yaml`](../api/index.yaml). Use OpenAPI for synchronous HTTP APIs, AsyncAPI for event-driven APIs, or a normative protocol-standard declaration where creating a synthetic OpenAPI document would be misleading. A Building Block with no API surface must declare that explicitly.

When one or more API surfaces are declared, map each active interface requirement to its operations, messages, or non-API verification in `api/coverage.yaml`. Follow the [GovStack Cross-BB API Design Guide](../api-design-guide/README.md) for conventions and validation.

Note that APIs should be grouped by functional area (from sections 4 and 6) where appropriate.

This section may link to rendered API documentation, but do not embed a second copy of a canonical contract in the GitBook assets.
{% endhint %}

{% hint style="info" %}
**Optional runtime catalogue discovery.** A deployment that publishes an API catalogue can use [RFC 9727, *api-catalog: A Well-Known URI and Link Relation to Help Discovery of APIs*](https://www.rfc-editor.org/rfc/rfc9727.html). Its `/.well-known/api-catalog` resource can direct clients to the deployment's canonical catalogue at any stable URI, allowing a deployment-specific catalogue path without requiring clients to know that path in advance.

This runtime discovery mechanism does not replace the canonical source contracts declared in `api/index.yaml`. An RFC 9727 implementation provides the required `application/linkset+json` representation and can make additional catalogue formats available through content negotiation.
{% endhint %}

## 8.1 Administrative APIs

## 8.2 User APIs
