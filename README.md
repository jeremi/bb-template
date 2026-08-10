# GovStack Building Block Template

This template is intended to be used by the various GovStack building block
repos. Each building block repo will have at least 4 main sections, outlined in
the directory structure below.

## Gitbook and the published "Building Block Specifications" document

Note that pushes to the `main` branch will automatically trigger a Gitbook build
and deployment from the `/spec` directory.

## Repo Structure

```sh
README.md
/spec # the markdown files which are used to build the specification in GitBook
/api # the API inventory, contracts, coverage mapping, and common components
/api-design-guide # cross-BB API design guidance and validation tooling
/test # the test plan and tests
  plan.md
/examples # examples for deploying, configuring, and testing applications which implement the behaviors specified by this building block
  /application-a
    README.md # instructions for deployment/testing
    docker-compose.yaml # example deployment file
      db
      web
      adaptor
      security-server
    Caddyfile # example config for "adaptor"
    Dockerfile # dockerfile to build "adaptor"
  /application-b
  /application-c
```

## API contracts

The template repository itself does not define a Building Block API surface, so
[`api/index.yaml`](api/index.yaml) declares `noApi`. When creating a Building
Block specification, replace that declaration with an inventory of every
OpenAPI, AsyncAPI, or normative protocol-standard surface. A Building Block
that genuinely has no API keeps an explicit `noApi` declaration.

When one or more API surfaces are declared, map active interface requirements
to their operations, messages, or non-API verification in `api/coverage.yaml`.
Follow the
[GovStack Cross-BB API Design Guide](api-design-guide/README.md) and use its
[validation instructions](api-design-guide/guides/validating-your-spec.md)
before requesting review. Reusable schemas are available under `api/common/`.

## ORB setup

Documentation for ORB setup is available here:
[ORB setup instruction](https://govstack-global.atlassian.net/wiki/spaces/GH/pages/191692823/ORB+setup+instruction)
