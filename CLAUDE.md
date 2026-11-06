# Brevo Gear: instructions for Claude sessions

Brevo Gear is a static internal tool hub (GitHub Pages, repo `nethaneelbaptiste-dot/brevo-gear`, branch `main`, public). Live: https://nethaneelbaptiste-dot.github.io/brevo-gear/

## Structure
- `index.html` hub, `modules/<module>/index.html` module page, `modules/<module>/<tool>.html` one self-contained tool per file. Relative links only, no build step.
- Modules: `crm` (Contacts model replication, Custom objects model comparison), `mcp` (MCP Prompt Runner). CDP, LTY, WLT are "coming soon" cards.
- New tool: start from `templates/tool-template.html`, add a card in the module index, check links with `python3 -m http.server`, push to `main`.

## Rules
- Never commit API keys, MCP tokens or customer data. Keys live in tab memory only; never ask for them in chat; log at most the last four characters.
- Real Brevo calls go from the browser to `https://api.brevo.com/v3` (CORS verified from the Pages origin). Do not publish tools as Claude artifacts for real accounts: their CSP blocks `api.brevo.com`.
- Destructive actions: dry run by default, typed confirmation before deletes.
- Edit tools in place; do not create a second copy.

## Context and history (Claude project "Brevo Gear")
Specs, skills and decisions live in the Claude project docs under `CRM Models/`: `Brevo Gear micro-app structure.md`, `Brevo Contacts model replication/` (spec, SKILL.md, assets), `Brevo MCP Prompt Runner/`. Read the relevant doc before changing a tool, and write decisions back there after the work (project instruction: save outputs as a skill and as a spec).
Skills: `brevo-gear` (hub conventions), `brevo-contacts-model-sync`, `brevo-custom-object-model-sync`.

## Brand
Brevo tokens: brand #004228, band #C0FFA5, CRM #0B996E, MCP #004228, CDP #1EB8B8, LTY #FDC802, WLT #6358DE. Fonts Alexandria (headings) and Inter. Light and dark via `prefers-color-scheme`.
