# Security Policy

dotclaude (https://github.com/poshan0126/dotclaude) is a collection of local Claude Code configuration files and shell scripts — agents, skills, rules, and hooks. It runs entirely on your machine and has no servers or telemetry (see [PRIVACY.md](PRIVACY.md)).

## Scope

The security-relevant surface is the shell hooks under `hooks/` — especially the PreToolUse guards (`block-dangerous-commands.sh`, `protect-files.sh`, `scan-secrets.sh`, `warn-large-files.sh`) that gate tool calls. Reports of interest include:

- A guard that can be bypassed to allow a dangerous command, a write to a protected/secret file, or a leaked credential.
- A hook that fails open when it should fail closed (or vice-versa) in a way that removes a safety guarantee.
- A skill or agent instruction that could be steered into running a destructive or exfiltrating command.

## Report a vulnerability

Open an issue at https://github.com/poshan0126/dotclaude/issues/new and add the `security` label. Include the affected file, the conditions to reproduce, and the impact. If you'd prefer not to disclose details publicly first, open a minimal issue asking for a private channel and we'll follow up.

Please do not include real secrets or credentials in a report — the secret-scan fixtures in this repo are deliberately fake, and yours should be too.

## Supported versions

Fixes land on `main` and ship in the next plugin version bump. There is no separate long-term support branch.
