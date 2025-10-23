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
