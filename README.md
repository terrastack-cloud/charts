# Terrastack Helm Charts

Helm charts for the Terrastack platform.

## Build locally

Requirements:

- Helm 3

```sh
helm lint charts/*
mkdir -p dist
helm package charts/* --destination dist
```

Render the bootstrap chart locally:

```sh
helm template tenant-bootstrap ./charts/tenant-bootstrap \
  --namespace tenant-example
```

## Charts

- `tenant-bootstrap`: namespace quota and baseline network policies.

## CI

GitHub Actions runs Helm linting, template rendering, and packaging on every
pull request and push to `main`. Packaged charts are uploaded as workflow
artifacts for successful `main` builds.

