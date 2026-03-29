# TODOs

## OpenAI Assistants API setup script

Create a script that programmatically uploads SKILL.md, scripts/rizzforms, and
references/api.md to the OpenAI Assistants API and creates a RizzForms assistant.
The Assistants API natively supports .md and .sh file uploads, making it the most
automatable web platform target.

**Why:** Assistants API is the only web platform where installation can be fully
automated (no manual paste/upload). Good candidate for `npx rizzforms-assistant setup`.

**Depends on:** OpenAI API key and Assistants API access.

## Smoke-test unverified platforms

Test the skill on: Goose, Windsurf, OpenClaw, OpenAI Codex CLI. For each platform,
verify that the agent discovers SKILL.md, reads it, and can execute the bundled CLI.
Add verified platforms to INSTALLATION.md.

**Why:** The current "generic agent" instructions are guesses. Real smoke tests
confirm whether each platform actually works.

## Auto-generate PROMPT.md from source files

Create a GitHub Action or build script that generates PROMPT.md from SKILL.md +
references/api.md automatically. This prevents drift between the two artifacts.

**Why:** PROMPT.md is a flattened subset of SKILL.md + api.md. Manual sync will
eventually diverge. A generation script keeps them in sync on every commit.
