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
| `pinVersions` | `false` | Preserve semver ranges (e.g., `^1.0.0`) |
| `customManagers:biomeVersions` | - | Auto-update `$schema` in `biome.json` |
| Security vulnerabilities | Priority | Security updates bypass all schedules and `minimumReleaseAge` restrictions |
| Biome grouping | - | Groups `@biomejs/biome` with `biome.json` schema updates |
