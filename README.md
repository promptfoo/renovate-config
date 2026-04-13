# Renovate Config

Shared [Renovate](https://docs.renovatebot.com/) configuration for the promptfoo organization.

## Usage

Add this to your repository's `renovate.json`:

```json
{
  "extends": ["local>promptfoo/renovate-config"]
}
```

Or extend it alongside other settings:

```json
{
  "extends": ["local>promptfoo/renovate-config"],
  "packageRules": [
    {
      "description": "Your repo-specific rules here"
    }
  ]
}
```

## What's Included

| Setting | Value | Description |
|---------|-------|-------------|
| `config:recommended` | - | Renovate's recommended base config |
| `:disableDependencyDashboard` | - | No dashboard issue created |
| `rangeStrategy` | `replace` | Preserve semver ranges instead of pinning versions |
| `customManagers:biomeVersions` | - | Auto-update `$schema` in `biome.json` |
| `helpers:pinGitHubActionDigests` | - | Pins GitHub Actions to commit SHAs so Renovate can open digest updates when an action tag moves |
| GitHub Actions release age | `3 days` | Wait briefly before opening GitHub Actions update PRs so fresh action changes can settle |
| `vulnerabilityAlerts` | Immediate | Security PRs bypass scheduling and `minimumReleaseAge` delays |
| Biome pinning | `pin` | Pins `@biomejs/biome` so installed Biome matches the schema version |
| Biome grouping | - | Groups `@biomejs/biome` with `biome.json` schema updates |
| GitHub Actions updates | Monthly | Schedules `github-actions` updates once per month |

## Validation

Validate the shared config locally with Renovate's official validator:

```sh
npx --yes --package renovate -- renovate-config-validator default.json
```

Pull requests are also checked automatically by GitHub Actions.
