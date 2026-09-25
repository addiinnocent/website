# Agent Instructions

This repository is managed through the Performance Dudes workspace. Do not bypass
repository-specific setup, signing, merge, secret, or workflow rules.

If a nested directory contains another `AGENTS.md`, read and follow that file for
work in that subtree.

## Project

Performance Dudes marketing website. Next.js 15 + TypeScript + Tailwind CSS 4.

## Key files

- `src/app/page.tsx` - Home page with all main content
- `src/app/imprint/page.tsx` - Legal imprint
- `src/app/layout.tsx` - Root layout and metadata
- `content-decisions/` - Documents all content choices and their rationale

## Content rules

- All copy must align to identity and strategy docs in the orga repo
- Speak about us, not against competitors
- CEO-readable first, technical second
- No em dashes. Use periods, commas, or restructure the sentence.
- No emojis unless explicitly requested
- Broader than software dev: we serve engineering, operations, security, and non-IT teams
- Honest tone: say what AI can and can't do

## Code rules

- Keep it simple. Content-first, minimal abstractions.
- No component library yet. Plain Tailwind on semantic HTML.
- Static pages only for now. No client-side state, no API routes.
- German legal requirements: imprint page must stay TMG-compliant.

## Workflow

- Use PRs, never push directly to main
- Commits follow conventional commits (`feat:`, `fix:`, `docs:`, `refactor:`, `style:`)
- Commit bodies must explain **why** the change was made and what motivated it
- Content changes should reference the relevant content decision or orga doc

## Codex

- Codex does not load the Claude plugin system from `.claude/settings.json`.
- Use `agent-sync` through `~/.config/agent-sync/settings.json` and the
  `clients.profiles.codex` commands.
- When using the shared channel, run `agent-sync start` and `agent-sync status`,
  then poll the relevant group with `agent-sync poll <group>`. For this repo,
  `<group>` is usually `website`; if unsure, inspect `agent-sync config` and
  `agent-sync status`.
- Poll before taking shared-repo work and before the final response. Send agent
  messages with `agent-sync send <group> "<message>"`; send Signal messages to
  humans with `agent-sync send --signal <group> "<message>"`.
