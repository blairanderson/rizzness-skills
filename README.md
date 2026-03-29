# RizzForms Skill for Claude

A [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills) that lets Claude create forms, configure webhook delivery, manage submissions, and generate embed HTML using the [RizzForms](https://www.rizzness.com) API.

## What it does

- Creates forms via the RizzForms API
- Configures webhook plugins with HMAC-SHA256 signing
- Tests the full submission-to-delivery pipeline
- Generates HTML forms styled for your CSS framework (Tailwind, Bootstrap, plain CSS)
- Views and searches submissions and spam
- Manages form settings, plugins, and signing secret rotation

## Install

```bash
claude skill add --from https://github.com/blairanderson/rizzness-skills
```

## Setup

1. Sign up at [forms.rizzness.com](https://forms.rizzness.com/signup)
2. Create an API key with the **admin** role in Account Settings
3. Set the environment variable:
   ```bash
   export RIZZFORMS_API_KEY="frk_your_key_here"
   ```

## Usage

Once installed, just ask Claude to do form-related things:

- "Add a contact form to my site"
- "Create a feedback form with a webhook to my API"
- "Show me recent form submissions"
- "Set up a waitlist signup form"

Claude will use the skill automatically when it recognizes form-related tasks.

## Skill structure

```
├── SKILL.md              # Main instructions Claude follows
├── scripts/
│   └── rizzforms         # Bundled CLI for all API operations
└── references/
    └── api.md            # Full API reference, webhook signing, framework quick-starts
```

## Bundled CLI

The skill includes a bash CLI that handles authentication and all API operations. Claude uses it automatically, but you can also use it directly:

```bash
rizzforms forms                          # List all forms
rizzforms forms:create "Contact Form"    # Create a form
rizzforms test <token>                   # Send a test submission
rizzforms submissions --form <token>     # View submissions
rizzforms plugins:create <token> <url>   # Add a webhook
```

Run `rizzforms help` for the full command list.

## Links

- [RizzForms](https://www.rizzness.com) — Form backend service
- [Documentation](https://www.rizzness.com/docs.md) — Full API docs
- [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills) — How skills work
