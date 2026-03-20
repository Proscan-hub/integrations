# VS Code — Proscan Extension

## Install

1. Open VS Code
2. Go to Extensions (Ctrl+Shift+X)
3. Search for **Proscan**
4. Click **Install**

## Configure

1. Open Settings (Ctrl+,)
2. Search for "Proscan"
3. Set **Server URL** to your Proscan instance URL
4. Set **API Token** to a token generated from Proscan (Settings > API Tokens)

Or add to your `settings.json`:

```json
{
  "proscan.serverUrl": "http://your-proscan-host:18080",
  "proscan.apiToken": "your-api-token"
}
```

## Usage

Once connected, the extension shows findings as inline diagnostics in your editor. Warnings and errors appear in the Problems panel, with details available on hover.

**Features:**
- Findings displayed as squiggly underlines with severity-based colors
- Hover over a finding for the description, CWE, and fix suggestion
- Quick-fix actions for supported vulnerability types
- Scan current file or project from the command palette (Ctrl+Shift+P > "Proscan: Scan")
- Results sync automatically when scans complete on the server

## Troubleshooting

- **"Connection refused"** — check that the server URL is correct and Proscan is running
- **"Unauthorized"** — regenerate your API token and update the extension settings
- **No findings showing** — make sure the project has been scanned at least once in Proscan
