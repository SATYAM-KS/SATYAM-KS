# GitHub Analytics Setup

The workflow in `.github/workflows/update-analytics.yml` generates static SVG analytics inside the repository.

## Recommended: add a Personal Access Token

For the most complete contribution/private-repository statistics:

1. GitHub → Settings → Developer settings → Personal access tokens
2. Create a classic PAT with the required `repo` and `read:user` scopes.
3. In this repository:
   Settings → Secrets and variables → Actions
4. Create:
   `PROFILE_STATS_TOKEN`
5. Paste the token as the secret value.

The workflow falls back to `GITHUB_TOKEN` if `PROFILE_STATS_TOKEN` is not configured, so public statistics can still be generated.

## Run it immediately

Go to:

Actions → Update GitHub Profile Analytics → Run workflow

After the first successful run, these files should appear:

- `profile/stats.svg`
- `profile/streak.svg`
- `profile/top-langs.svg`
- `profile/contributions.svg`

The workflow then refreshes the cards daily at 03:00 UTC (08:30 IST).
