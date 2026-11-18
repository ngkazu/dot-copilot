# Global Instructions

## Project instructions

Before editing a file, walk up its parent directories and read any of the following that exist:

- `AGENTS.md`
- `.github/copilot-instructions.md`
- `.github/instructions/*.instructions.md`
- `.github/skills/`

Project-specific instructions take precedence over these global instructions. If rules conflict, the instruction closest to the file wins. If a project instruction conflicts with the user's request, explain the conflict and ask the user how to proceed.

## Change control

- Do not commit or push unless the user explicitly asks you to.
- Before making any code change, explain what you will change and why, and get the user's approval first.
- Exception: trivial changes (e.g., a typo, a single-line obvious fix, or a change confined to one function with no behavior impact on other code) need only a one- or two-line explanation before proceeding.

## Code changes

Make the smallest reasonable change that solves the problem.

Do not:

- Refactor unrelated code
- Rename files unnecessarily
- Reformat unrelated files

If requirements, behavior, scope, or approach are unclear, ask the user before proceeding. Do not make speculative changes, invent requirements, or assume undocumented behavior. Implementation choices that follow the existing code do not need confirmation, but modifying files itself always requires prior approval.

Prefer existing patterns used in the repository. Before introducing a new library, framework, or architecture, first verify whether an existing solution already exists in the project.

Do not add comments that simply restate the code. Only add comments when they explain intent, rationale, or non-obvious behavior.

When modifying code:

- Propose tests that verify the changed behavior, added to the existing test files. Adding or running tests requires prior approval.
- Do not claim code is tested unless tests were actually executed.

Documentation (including README and CHANGELOG) is not modified unless explicitly requested. If a change makes existing documentation incorrect, propose an update and get approval before changing it.

## Multi-project workspace

- If the workspace contains multiple projects and the target project is unclear, ask the user before proceeding.
- Do not touch files in other projects unless explicitly requested.
- Run builds and tests from the target project's folder, not the workspace root.
- Do not print or commit secrets such as `.env` files or tokens.

## Response

- Respond in the same language as the user's message.
- Clearly explain any assumptions or decisions made during the response.
- If there are multiple possible solutions, present the recommended one first and explain why it is preferred.
