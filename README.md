# Agent Skills (Plugin Edition)

> **Fork of [mattpocock/skills](https://github.com/mattpocock/skills)** by [Matt Pocock](https://github.com/mattpocock). All skills, descriptions, and content are his original work. This fork only repackages them as a Claude Code plugin — no skill content has been modified.
>
> **If Matt Pocock publishes an official plugin package, switch to that instead.** This fork is a stopgap until the upstream repo adopts plugin packaging.

## Why this fork?

The original repository distributes skills individually via `npx skills@latest add`. That works well for cherry-picking, but there is no way to install all 19 skills at once.

This fork reorganizes the directory structure so the entire collection can be installed in one step — either by copying files directly, or via Claude Code's plugin system.

## Installation

### Option 1: Clone and copy (simplest)

```bash
git clone https://github.com/dstroe2000/mattpocock_skills.git
cp -r mattpocock_skills/skills/* ~/.claude/skills/
```

Claude Code automatically discovers any `SKILL.md` files in `~/.claude/skills/`. No config needed, no dependencies beyond git.

### Option 2: Install individual skills from upstream (original method)

Install only the skills you want, directly from [Matt Pocock's repo](https://github.com/mattpocock/skills) — see the listings below.

### Option 3: Plugin system (experimental)

The Claude Code plugin system is still young but allows bundled install, update, and namespacing. Use this if you prefer managed plugins over manual file copying.

**Via plugin commands:**

```
/plugin marketplace add dstroe2000/mattpocock_skills
/plugin install mattpocock@mattpocock-skills
```

**Or manually in `~/.claude/settings.json`:**

```json
{
  "enabledPlugins": {
    "mattpocock@mattpocock-skills": true
  },
  "extraKnownMarketplaces": {
    "mattpocock-skills": {
      "source": {
        "source": "github",
        "repo": "dstroe2000/mattpocock_skills"
      }
    }
  }
}
```

Then restart Claude Code. Skills will be available as `mattpocock:<skill-name>`.

---

## Credits

All skills below were created by **[Matt Pocock](https://github.com/mattpocock)**. This fork exists solely to provide a bulk installation method and does not modify any skill content.

---

A collection of agent skills that extend capabilities across planning, development, and tooling.

## Planning & Design

These skills help you think through problems before writing code.

- **write-a-prd** — Create a PRD through an interactive interview, codebase exploration, and module design. Filed as a GitHub issue.

  ```
  npx skills@latest add mattpocock/skills/write-a-prd
  ```

- **prd-to-plan** — Turn a PRD into a multi-phase implementation plan using tracer-bullet vertical slices.

  ```
  npx skills@latest add mattpocock/skills/prd-to-plan
  ```

- **prd-to-issues** — Break a PRD into independently-grabbable GitHub issues using vertical slices.

  ```
  npx skills@latest add mattpocock/skills/prd-to-issues
  ```

- **grill-me** — Get relentlessly interviewed about a plan or design until every branch of the decision tree is resolved.

  ```
  npx skills@latest add mattpocock/skills/grill-me
  ```

- **design-an-interface** — Generate multiple radically different interface designs for a module using parallel sub-agents.

  ```
  npx skills@latest add mattpocock/skills/design-an-interface
  ```

- **request-refactor-plan** — Create a detailed refactor plan with tiny commits via user interview, then file it as a GitHub issue.

  ```
  npx skills@latest add mattpocock/skills/request-refactor-plan
  ```

## Development

These skills help you write, refactor, and fix code.

- **tdd** — Test-driven development with a red-green-refactor loop. Builds features or fixes bugs one vertical slice at a time.

  ```
  npx skills@latest add mattpocock/skills/tdd
  ```

- **triage-issue** — Investigate a bug by exploring the codebase, identify the root cause, and file a GitHub issue with a TDD-based fix plan.

  ```
  npx skills@latest add mattpocock/skills/triage-issue
  ```

- **improve-codebase-architecture** — Explore a codebase for architectural improvement opportunities, focusing on deepening shallow modules and improving testability.

  ```
  npx skills@latest add mattpocock/skills/improve-codebase-architecture
  ```

- **migrate-to-shoehorn** — Migrate test files from `as` type assertions to @total-typescript/shoehorn.

  ```
  npx skills@latest add mattpocock/skills/migrate-to-shoehorn
  ```

- **scaffold-exercises** — Create exercise directory structures with sections, problems, solutions, and explainers.

  ```
  npx skills@latest add mattpocock/skills/scaffold-exercises
  ```

## Tooling & Setup

- **setup-pre-commit** — Set up Husky pre-commit hooks with lint-staged, Prettier, type checking, and tests.

  ```
  npx skills@latest add mattpocock/skills/setup-pre-commit
  ```

- **git-guardrails-claude-code** — Set up Claude Code hooks to block dangerous git commands (push, reset --hard, clean, etc.) before they execute.

  ```
  npx skills@latest add mattpocock/skills/git-guardrails-claude-code
  ```

## Writing & Knowledge

- **write-a-skill** — Create new skills with proper structure, progressive disclosure, and bundled resources.

  ```
  npx skills@latest add mattpocock/skills/write-a-skill
  ```

- **edit-article** — Edit and improve articles by restructuring sections, improving clarity, and tightening prose.

  ```
  npx skills@latest add mattpocock/skills/edit-article
  ```

- **ubiquitous-language** — Extract a DDD-style ubiquitous language glossary from the current conversation.

  ```
  npx skills@latest add mattpocock/skills/ubiquitous-language
  ```

- **obsidian-vault** — Search, create, and manage notes in an Obsidian vault with wikilinks and index notes.

  ```
  npx skills@latest add mattpocock/skills/obsidian-vault
  ```
