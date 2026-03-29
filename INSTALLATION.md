# Installation

Pick your platform:

[Claude Code](#claude-code) | [Cursor](#cursor) | [Gemini CLI](#gemini-cli) | [VS Code / Copilot](#vs-code--github-copilot) | [ChatGPT Custom GPT](#chatgpt-custom-gpt) | [Claude Project](#claude-project) | [Other](#other-agents)

**Download ZIPs:** [rizzforms-prompt.zip](https://github.com/blairanderson/rizzness-skills/releases/latest/download/rizzforms-prompt.zip) (web platforms) | [rizzforms-skill.zip](https://github.com/blairanderson/rizzness-skills/releases/latest/download/rizzforms-skill.zip) (local agents)

---

## Claude Code

**Personal skill** (available in all your projects):

```bash
git clone https://github.com/blairanderson/rizzness-skills.git ~/.claude/skills/rizzforms
```

**Project skill** (available only in one project):

```bash
git clone https://github.com/blairanderson/rizzness-skills.git .claude/skills/rizzforms
```

Verify: ask Claude "list my forms" — it should use the RizzForms CLI.

---

## Cursor

Clone into your project:

```bash
git clone https://github.com/blairanderson/rizzness-skills.git .cursor/skills/rizzforms
```

Verify: ask Cursor to "create a contact form with RizzForms."

---

## Gemini CLI

Clone into your project:

```bash
git clone https://github.com/blairanderson/rizzness-skills.git .gemini/skills/rizzforms
```

Verify: ask Gemini to "set up a feedback form."

---

## VS Code / GitHub Copilot

Copilot uses `.github/copilot-instructions.md` for custom instructions. Copy the
contents of `PROMPT.md` and append it to your existing instructions file:

```bash
cat PROMPT.md >> .github/copilot-instructions.md
```

Or if you don't have one yet:

```bash
mkdir -p .github
cp PROMPT.md .github/copilot-instructions.md
```

Verify: ask Copilot Chat to "add a contact form to my site."

---

## ChatGPT Custom GPT

1. Download [rizzforms-prompt.zip](https://github.com/blairanderson/rizzness-skills/releases/latest/download/rizzforms-prompt.zip) and extract it
2. Go to [ChatGPT](https://chatgpt.com) > Explore GPTs > Create
3. In the **Instructions** field, paste the contents of `PROMPT.md`
4. Upload all extracted files as **Knowledge** files:
   - `PROMPT.md` — core skill instructions
   - `references/api.md` — full API reference, webhook signing, framework quick-starts
   - `scripts/rizzforms` — CLI reference (ChatGPT can read this to understand available commands)
5. Save your GPT

Verify: ask your GPT "create a waitlist signup form."

---

## Claude Project

1. Download [rizzforms-prompt.zip](https://github.com/blairanderson/rizzness-skills/releases/latest/download/rizzforms-prompt.zip) and extract it
2. Go to [claude.ai](https://claude.ai) > Projects > New Project
3. In **Project Instructions**, paste the contents of `PROMPT.md`
4. Save the project

Note: Claude Projects does not support `.md` file uploads directly. Paste the content
into the instructions field, or rename to `.txt` before uploading as a knowledge file.

Verify: ask Claude "set up a contact form with webhook delivery."

---

## Other Agents

For any AI agent that reads markdown instructions:

1. Clone the repo: `git clone https://github.com/blairanderson/rizzness-skills.git`
2. Point your agent at `SKILL.md` (for agents that can run bash and read multiple files)
3. Or use `PROMPT.md` (for agents that need a single self-contained instruction file)

---

## API Key Setup

All platforms need a RizzForms API key:

1. Sign up at [forms.rizzness.com/signup](https://forms.rizzness.com/signup)
2. Go to Account Settings > API Keys > Create API Key (select **Admin** role)
3. Set the environment variable:
   ```bash
   export RIZZFORMS_API_KEY="frk_your_key_here"
   ```

For web platforms (ChatGPT, Claude Projects), tell the assistant your API key when
you start a conversation, or include it in the instructions.

---

## Updating

**Local agents:** `cd` into the skill directory and pull:

```bash
cd ~/.claude/skills/rizzforms && git pull
```

**Web platforms:** Re-paste the latest `PROMPT.md` contents into your instructions.

---

## Unverified Platforms

These platforms may work with the generic instructions above but haven't been tested:
Goose, Windsurf, OpenClaw, OpenAI Codex CLI.

If you get it working on a new platform,
[open a PR](https://github.com/blairanderson/rizzness-skills/pulls) with install
instructions and we'll add it to this guide.
