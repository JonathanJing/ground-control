---
name: ground-control
description: Post-upgrade verification system for OpenClaw. Defines a model/cron/channel ground truth file and a 5-phase automated verification flow (config integrity, API key liveness, cron integrity, session smoke test, channel liveness) with auto-repair for config and cron drift.
version: "0.1.0"
metadata:
  author: JonathanJing
  tags: [ops, verification, upgrade, config, cron, health]
  license: MIT
---

# ground-control

Post-upgrade verification for OpenClaw. Keeps your system honest after every upgrade.

## When to use

- After running `openclaw update` or `npm install -g openclaw@latest`
- When you suspect config drift (model changed, cron broken, channel down)
- Periodic health check via `/verify` command

## Setup

1. Copy `templates/MODEL_GROUND_TRUTH.md` to your workspace root
2. Fill in your actual config values (models, cron jobs, channels)
3. Add the GROUND_TRUTH sync rule to your AGENTS.md (see README)
4. Run `/verify` to test

## Files

- `templates/MODEL_GROUND_TRUTH.md` — Ground truth template (copy to workspace root)
- `scripts/post-upgrade-verify.md` — Agent execution prompt for 5-phase verification
- `scripts/UPGRADE_SOP.md` — Upgrade standard operating procedure
