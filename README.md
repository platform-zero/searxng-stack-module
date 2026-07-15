# SearXNG stack module

- Module id: `searxng`
- Module repo: `searxng-stack-module`
- Lifecycle: `active`
- Route: `https://websearch.${DOMAIN}`

## Owned overlays
- `stack.runtime.yaml`
- `stack.config/components.json`
- `stack.config/service-contracts.json`
- `stack.config/searxng/settings.yml`

## Behavior

The module runs the official SearXNG container as a rootless daemon behind the
shared Caddy/Keycloak route. The instance enables HTML and JSON output formats
for browser and API use. `search.${DOMAIN}` remains owned by the OpenSearch
backend route.

## Required secrets

- `SEARXNG_SECRET`

## Validation

```sh
./tests/validate.sh
./tests/contract.sh
```

## Lifecycle

`active` modules are expected to keep `stack.module.json`, owned overlays, and
`tests/validate.sh` in sync.
