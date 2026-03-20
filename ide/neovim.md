# Neovim — Proscan LSP

Proscan provides a Language Server Protocol (LSP) server. Any LSP-compatible editor can connect to it. Below is the Neovim configuration.

## Prerequisites

- Neovim 0.8+
- An LSP client plugin (nvim-lspconfig recommended)

## Configuration

Add to your Neovim config (`init.lua` or equivalent):

```lua
local lspconfig = require('lspconfig')
local configs = require('lspconfig.configs')

if not configs.proscan then
  configs.proscan = {
    default_config = {
      cmd = { 'proscan-lsp' },
      filetypes = {
        'javascript', 'typescript', 'python', 'go', 'java',
        'ruby', 'php', 'c', 'cpp', 'rust', 'yaml', 'json',
        'terraform', 'dockerfile',
      },
      root_dir = lspconfig.util.root_pattern('.git', 'package.json', 'go.mod'),
      settings = {
        proscan = {
          serverUrl = 'http://your-proscan-host:18080',
          apiToken = 'your-api-token',
        },
      },
    },
  }
end

lspconfig.proscan.setup({})
```

## Usage

Once connected, findings appear as standard LSP diagnostics — inline warnings in the buffer, entries in the quickfix list, and details available through `vim.lsp.buf.hover()`.

## Sublime Text

Sublime Text users can connect to the same LSP server using the [LSP package](https://github.com/sublimelsp/LSP). Configure the `proscan-lsp` command as a custom language server in your LSP settings.
