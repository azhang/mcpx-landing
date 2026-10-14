# MCP Server Directory

A minimal directory listing MCP servers available at mcp.x.zip using streamable HTTP transport.

## Features

- Clean, minimal UI with automatic light/dark mode
- Client-specific installation instructions for:
  - Claude Desktop
  - Claude Code
  - OpenAI Codex
  - Cursor
  - ChatGPT
- Click-to-copy installation commands
- Mobile responsive design
- Single HTML file with no build process

## Deployment

This is a static site that can be deployed anywhere:

### GitHub Pages

1. Push to a GitHub repository
2. Go to Settings → Pages
3. Select source branch
4. Site will be live at `https://username.github.io/repo-name`

### Netlify

1. Drag and drop the folder to Netlify
2. Or connect your GitHub repo
3. Site deploys automatically

### Vercel

```bash
npm i -g vercel
vercel
```

### Custom Domain

Point your domain to the hosting provider and configure DNS settings.

## Adding More Servers

Edit the `servers` array in `index.html`:

```javascript
const servers = [
    {
        name: 'Server Name',
        description: 'What the server does',
        url: 'https://mcp.x.zip/server-name/mcp'
    },
    // Add more servers...
];
```

## Local Development

Simply open `index.html` in your browser. No build step required.

## Browser Support

Works in all modern browsers with support for:
- CSS custom properties
- CSS Grid/Flexbox
- `prefers-color-scheme` media query
- Clipboard API

## Plugin marketplace

This repo is also a plugin marketplace (`mcpx`). Each plugin bundles a server from this site with its skill, and lives in that server's own repo under `plugins/<name>/`, in both formats: Claude Code (`.claude-plugin/plugin.json`) and [Agent Plugins](https://agent-plugins.org) (`plugin.json` + `mcp.json`). This repo only lists them:

- `.claude-plugin/marketplace.json`: Claude Code, claude.ai, Cowork
- `.agents/plugins/marketplace.json`: Codex and other Agent Plugins clients

| Plugin | Source |
|---|---|
| `deribit` | [azhang/deribit-mcp](https://github.com/azhang/deribit-mcp/tree/main/plugins/deribit) |
| `polymarket` | azhang/polymarket-mcp (private for now) |

Install:

- **claude.ai / desktop app / Cowork:** Customize → Plugins → Add → Add marketplace → `azhang/agent-plugins`
- **Claude Code:** `/plugin marketplace add azhang/agent-plugins`, then `/plugin install deribit@mcpx`
- **Codex:** `codex plugin marketplace add azhang/agent-plugins`, then install `deribit` from the `mcpx` marketplace

To add a plugin: put it in its server's repo under `plugins/<name>/` with both manifests, add an entry to both marketplace files here, and run `claude plugin validate .`.
