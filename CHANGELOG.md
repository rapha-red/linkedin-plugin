# Changelog

## 1.0.0 (2026-09-30)

First release.

- Nine task skills (`linkedin-setup`, `linkedin-post`, `linkedin-humanize`, `linkedin-comment`, `linkedin-reply`,
  `linkedin-dm`, `linkedin-inbox`, `linkedin-plan`, `linkedin-profile`) and the `linkedin` entry skill.
- Shared references: guardrails, voice, conversations, evidence (graded A, B, C and myths), persona template,
  log format, the optional LinkedIn connection.
- Personas and an append-only log per persona, kept locally in `~/.linkedin-plugin/`.
- Manifests for Claude Code, Claude Desktop and claude.ai, and Codex; plain skill folders for other agents.
- Behaviour checks in `evals/`.
