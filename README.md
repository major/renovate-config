# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) configuration inherited by all repos in the `major` GitHub organization.

## Usage

Repos inherit this config automatically via Renovate's [org-level inherited config](https://docs.renovatebot.com/config-presets/#organization-level-presets). No per-repo setup needed.

If a repo needs to override or extend, add a `renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["local>major/renovate-config:org-inherited-config"]
}
```

## What's configured

**Base:** `config:best-practices` (includes `config:recommended`, Docker/GitHub Actions digest pinning, lockfile maintenance, semantic commits, and more).

**Schedule:** Mondays before 3 AM (America/Chicago).

**Rules:**

- 7-day minimum release age on all updates (cooldown period)
- Auto-merge disabled globally (including GitHub-native `platformAutomerge`)
- `Signed-off-by` trailer on all Renovate commits (`:gitSignOff`)
- Python dependency updates grouped into a single PR, labeled `python`
- Rust dependency updates grouped into a single PR, labeled `rust`
