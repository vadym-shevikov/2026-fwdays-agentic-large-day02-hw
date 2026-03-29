# Create component

Create a new React component in this repo following project conventions. **Clarify first** if the user did not specify: component name, target package/folder (`packages/excalidraw/`, `excalidraw-app/`, or other `packages/*`), and whether a test is required.

## Rules (required)

- **Only** functional components and hooks (no class components).
- **Export**: named (`export function ComponentName` or `export const ComponentName`), no `default export`.
- **Props type**: `type ComponentNameProps = { ... }` (or match sibling files in the same directory).
- **Component file**: `ComponentName.tsx` (PascalCase).
- **Colocated utilities**: kebab-case, e.g. `component-name-helpers.ts`, consistent with the module.
- **Test** (when appropriate): colocated `ComponentName.test.tsx`, aligned with existing tests in that package (Vitest / React Testing Library — follow neighboring `*.test.tsx`).
- **TypeScript**: strict; avoid `any` and `@ts-ignore` when avoidable; `import type` for types.
- **Imports and style**: match the nearest existing components in the same package (aliases, import order).

## Do not do without explicit request

- Modify `packages/excalidraw/scene/renderer.ts`, `packages/excalidraw/data/restore.ts`, `packages/excalidraw/actions/manager.ts`, or `packages/excalidraw/types.ts`.

## Output

- Show created or updated files with full content or clear diff snippets.
- Briefly state where the component lives and how to import it.

## Follow-up

- If the change materially affects project context, remind about updating the Memory Bank under `docs/memory/` per `AGENTS.md`.
- For verification steps, follow **How to verify** in `.cursor/rules/testing.mdc` and `.cursor/rules/conventions.mdc`.
