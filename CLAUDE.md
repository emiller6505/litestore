# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Rules

1. Never commit or push to git. You can use any non-destructive and non-write git operations such as git log and git diff without asking for permission first.
2. Never delete any code without asking the human first.
3. Never run npm publish or any other commands with remote impact. Keep it local.
4. You have permission to use any exploratory bash commands such as cd, less, grep, find, ls, etc.
5. Do not create and commit ephemeral markdown report files to the codebase. Keep the codebase as clean and tidy as possible.
6. When in doubt, ask permission.

## Project Overview

**webstate** is a zero-dependency, pure JavaScript global state library for client-side SPAs. Framework-agnostic core with adapter layers (e.g. React bindings) built on top.

## Constraints

- **Zero production dependencies** — no runtime deps in `package.json`. Dev dependencies (jest, etc.) are fine.
- **No TypeScript** — pure JavaScript only.
- **Atomic get/set** — reads return current value, writes replace it. No partial updates.
- **Idempotent** — same input produces same result; redundant sets don't trigger unnecessary side effects.
- **Configure once, access anywhere** — single store initialization, globally accessible.
