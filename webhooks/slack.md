# Slack Webhook Integration

Send Proscan scan notifications to a Slack channel.

## Setup

### 1. Create a Slack Incoming Webhook

1. Go to [Slack API — Incoming Webhooks](https://api.slack.com/messaging/webhooks)
2. Create a new app or select an existing one
3. Enable Incoming Webhooks
4. Add a webhook to your workspace and choose the target channel
5. Copy the webhook URL

### 2. Configure in Proscan

1. Go to **Settings > Integrations > Messaging**
2. Select **Slack**
3. Paste the webhook URL
4. Choose which events to send:
   - Scan completed
   - Critical findings detected
   - Quality gate failed
5. Save

### 3. Test

Run a scan. When it completes, a notification should appear in your Slack channel with a summary of the results.

## Message Format

Notifications include:
- Scan type and target
- Finding count by severity
- Quality gate status (pass/fail)
- Link to view full results in Proscan
