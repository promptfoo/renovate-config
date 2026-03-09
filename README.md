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
| `vulnerabilityAlerts` | Immediate | Security PRs bypass scheduling and `minimumReleaseAge` delays |
| Biome grouping | - | Groups `@biomejs/biome` with `biome.json` schema updates |

## Validation

Validate the shared config locally with Renovate's official validator:

```sh
npx --yes --package renovate -- renovate-config-validator default.json
```

Pull requests are also checked automatically by GitHub Actions.
