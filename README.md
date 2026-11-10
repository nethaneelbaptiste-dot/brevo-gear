# Brevo Gear

Static internal tool hub. Entry point: `index.html` -> `modules/<module>/index.html` -> tool pages.

```
index.html
modules/crm/index.html, contacts-model-sync.html, custom-object-model-sync.html, custom-object-delete-all.html
modules/mcp/index.html, mcp-prompt-runner.html
```

- No build step, no server code. All links are relative, so it works on GitHub Pages and from a local folder.
- API keys are typed in the page and kept in tab memory only. Never commit keys.
- Add a tool: drop a self-contained HTML file in `modules/<module>/`, add a card in that module's `index.html`.
- Deploy: Settings > Pages > Deploy from branch `main` / root. Set Pages visibility to private (organization members only).
