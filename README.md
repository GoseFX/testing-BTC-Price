# BTC price to Discord (hourly) via GitHub Actions

This posts the current BTC-USD spot price to a Discord channel every hour using a webhook. No server/hosting required.

Setup

1) Create a Discord Webhook
- In your server: go to the target channel > Edit Channel > Integrations > Webhooks.
- Create a new webhook and Copy Webhook URL.

2) Create a GitHub repository
- Create an empty repo (any name, public or private).
- Push this project to that repo (see commands below).

3) Add the Discord webhook as a GitHub Actions secret
- In your GitHub repo: Settings > Secrets and variables > Actions > New repository secret
- Name: DISCORD_WEBHOOK_URL
- Value: the webhook URL from step 1

4) Trigger the workflow manually to test
- Go to the Actions tab > "BTC hourly to Discord" > Run workflow.
- Then it will also run automatically every hour (UTC).

Change frequency/currency
- Schedule is set to hourly (cron: 0 * * * *). Adjust if desired.
- Currency pair is BTC-USD. Change the Coinbase URL to e.g. BTC-EUR.

Troubleshooting
- If nothing posts, check the Actions run logs for errors.
- Ensure the secret name matches exactly: DISCORD_WEBHOOK_URL.
- GitHub scheduled workflows can be a few minutes delayed.
