# Custom Webhook

For services not covered by built-in integrations, use a generic webhook to receive scan events.

## Setup in Proscan

1. Go to **Settings > Integrations > Webhooks**
2. Click **Add Webhook**
3. Enter your endpoint URL
4. Select the events to subscribe to
5. Save

## Payload Format

Proscan sends a POST request with a JSON body. The structure depends on the event type.

### Scan Completed

```json
{
  "event": "scan.completed",
  "timestamp": "2026-03-19T14:30:00Z",
  "scan": {
    "id": "abc123",
    "type": "sast",
    "target": "main-repo",
    "status": "completed",
    "findings": {
      "critical": 0,
      "high": 2,
      "medium": 5,
      "low": 12,
      "total": 19
    },
    "quality_gate": "passed"
  }
}
```

### Finding Created

```json
{
  "event": "finding.created",
  "timestamp": "2026-03-19T14:31:00Z",
  "finding": {
    "id": "def456",
    "severity": "high",
    "title": "SQL Injection in user query",
    "cwe": "CWE-89",
    "file": "src/db/users.go",
    "line": 42
  }
}
```

## Verifying Requests

Each webhook request includes an `X-Proscan-Signature` header containing an HMAC-SHA256 signature. Verify this against the secret shown in your webhook configuration to confirm the request came from your Proscan instance.

## Retries

If your endpoint returns a non-2xx response, Proscan retries with exponential backoff. Failed deliveries are logged in the webhook settings page.
