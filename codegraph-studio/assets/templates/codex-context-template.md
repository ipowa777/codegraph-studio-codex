# Codex Context

Use this file as a compact generated context for Codex.

## Mission

- Project purpose:
- Current objective:
- Latest validated step:

## Read First

- .project-map/preflight.md
- docs/README.md
- docs/roadmap.md
- .project-map/change-impact.md
- .project-map/access-matrix.md
- .project-map/agents-manifest.json

## Non-Negotiables

- Do not read or expose secrets.
- Do not version `.project-map/`.
- Run `npm run codegraph:preflight -- "target"` before sensitive changes.
- Keep public, user-private, admin-private, monitoring-private, and system surfaces separate.
- Use owner/admin checks for sensitive writes.
- Use human validation for destructive, payment, production, external publication, or irreversible actions.
- Treat `.project-map/scan-cache.json` as local generated state, not source truth.

## Validation

- npm run codegraph:preflight -- "target"
- npm run codegraph:scan
- npm run codegraph:security
- npm run codegraph:ci

## Optional MCP

- npm run codegraph:mcp
