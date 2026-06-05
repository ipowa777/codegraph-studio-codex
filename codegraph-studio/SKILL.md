---
name: codegraph-studio
description: Use when installing, auditing, or operating CodeGraph Studio in a software project: local project map, GraphView, security gates, access surfaces, AI agent registry, sub-agent handoff packets, impact analysis, docs cleanup, CI checks, and compact Codex context generation.
metadata:
  short-description: Project map, risk gates, GraphView, and compact Codex context
---

# CodeGraph Studio

Use this skill when the user wants to install or operate CodeGraph Studio in a project, improve development safety, reduce context/token usage, audit public/private/admin/monitoring surfaces, manage AI agents or sub-agents, or prepare CI gates around risky changes.

## Core Rule

Stay project-neutral. Do not mention or copy references to any source project, client, product, or private example when creating reusable CodeGraph files.

## Workflow

1. Inspect the target project first: git status, package manager, scripts, app structure, docs, tests, CI, data surfaces, agents, and auth boundaries.
2. Read `references/codegraph-reuse-directive.md` before implementing or adapting CodeGraph Studio.
3. Do a Phase 0 audit before installing code: P0/P1/P2 risks, docs inventory, dead code candidates, dependency/config issues, and access surfaces.
4. Fix P0 and P1 blockers before a full integration. If they cannot be fixed, install CodeGraph in read-only mode and mark the project as not healthy.
5. Install or adapt a local scanner that writes `.project-map/` and never sends code or secrets outside the workspace.
6. Add scripts equivalent to `codegraph:scan`, `codegraph:security`, `codegraph:query`, `codegraph:impact`, `codegraph:baseline`, `codegraph:diff`, `codegraph:ci`, and `codegraph:github`.
7. Generate compact contexts: `.project-map/ai-context.md`, `.project-map/codex-context.md`, and targeted `.project-map/handoff-packets/`.
8. Add CI gates for new blockers, unguarded private routes, exposed admin/monitoring surfaces, missing noindex, secrets, webhooks, payments, AI costs, and autonomous agents without limits.
9. Validate with the target project's normal test/build commands plus CodeGraph scan/security/ci.
10. Update the target roadmap or technical log after each validated step.

## When To Load References

- For full implementation details, load `references/codegraph-reuse-directive.md`.
- For CI, start from `assets/templates/github-action.yml`.
- For project configuration, start from `assets/templates/codegraph-config.example.json`.
- For Codex context output shape, start from `assets/templates/codex-context-template.md`.

## Non-Negotiables

- Never read, copy, log, or commit secrets.
- Never version `.project-map/` by default.
- Never delete files without explicit user validation.
- Keep generated AI contexts short and source-linked.
- Give sub-agents only the smallest handoff packet needed.
- Treat public, user-private, admin-private, monitoring-private, and system surfaces separately.
- Human validation is required for destructive, payment, production, mass email, external publication, or irreversible actions.
