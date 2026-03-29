---
name: codebase-explorer
description: Explores unfamiliar code areas read-only—maps directories, key files, data flow, and cross-package dependencies, then summarizes findings. Use when the user says explore, investigate, how does X work, or wants to understand a module, feature, or file pattern without modifying code.
---

# Skill: Codebase Explorer

## When to use

When you need to understand an unfamiliar area of the codebase.

Triggered by: "explore", "investigate", "how does X work?", or similar.

## Inputs

- Area of interest: module path, feature name, or file pattern (from the user or `@folder` / `@codebase` context)

## Steps

1. **Locate scope** — Identify relevant directories and files (search, glob, or user-attached paths). Prefer narrowing before deep reading.
2. **Read surface docs** — Open `README`, package docs, or top-of-file / module comments in that area when present.
3. **Map responsibilities** — List the main files and one-line roles (what each owns, not every symbol).
4. **Trace data flow** — Follow the path: entry point (API, CLI, hook, handler) → processing → output or side effects. Note important types or payloads at boundaries.
5. **Dependencies** — List notable imports: other packages in the monorepo, external libs, and config that gates behavior.
6. **Verify** — Tie claims to concrete code (file + symbol or line range). If uncertain, say so and point to what to read next.

## Outputs

Deliver a short summary containing:

- **Purpose** — What this area does in product/engineering terms
- **Key files** — Table or bullets: path → responsibility
- **Data flow** — Entry → steps → exit (bulleted chain)
- **Dependencies** — Internal packages vs external vs config
- **Deeper dive** — Ordered list of files worth opening next for detail work

## Safety

- **READ-ONLY** — Do not create, edit, or delete files during exploration.
- **Evidence-based** — Prefer quoted or cited code over assumptions; flag gaps explicitly.
