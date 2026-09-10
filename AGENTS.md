# Codex Repository Instructions

Before doing any work in this repository, read `CLAUDE.md` completely. It is
the canonical source for the website workflow, editable sources, render
command, validation, and publishing conventions.

When `CLAUDE.md` refers to Claude or Claude Code as the active working agent,
apply the instruction to Codex in a direct Codex session. Use Codex equivalents
for agent-specific tool names, but keep literal project paths, filenames,
commands, hooks, and environment variables unchanged unless the repository
provides a Codex-specific equivalent.

Codex and Claude Code are peer agents. The caller and requested outcome
determine Codex's role: direct build, fix, change, and operational requests
authorize implementation within scope; review and audit requests remain
read-only unless the user also asks for changes. When Claude Code invokes Codex
for an independent review, inspect the actual source and rendered diff, do not
modify files, and provide concrete corrections with exact locations.
