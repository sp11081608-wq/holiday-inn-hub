# Design & Scraping Tools (installed July 16, 2026)

## Design skills (in ~/.claude/skills/)
- **frontend-design** — official Anthropic skill (github.com/anthropics/skills). Use for ALL dashboard/UI/design work. Invoke with `/frontend-design` or let it auto-load.
- **shadcn** — official skill from the shadcn-ui/ui repo. Auto-triggers on shadcn/ui component work; deliberately not user-invocable.
- Both verified loading in Claude Code 2.1.187 on July 16, 2026 (frontend-design in the skills list; shadcn loads via the Skill tool).

## Firecrawl scraping (MCP)
- Server "firecrawl" added at user scope in ~/.claude.json → `npx -y firecrawl-mcp`, env `FIRECRAWL_API_KEY` currently the placeholder `fc-PASTE-YOUR-KEY-HERE`.
- **Not working until Shyam signs up free at firecrawl.dev and the real key replaces the placeholder** (Nelish has the exact steps; also in Documents/Setup/SETUPCHANGELOG.md, July 16, 2026 entry).
- Pending verification once keyed: test scrape of https://members.poolerchamber.com/eventcalendar.

## Update — July 16, 2026: Firecrawl LIVE
- Real API key installed in ~/.claude.json (replaces placeholder). Server shows Connected in claude mcp list.
- Fix applied: the shared npm cache (~/.npm) has root-owned files that broke npx; firecrawl now uses its own cache via npm_config_cache=~/.npm-firecrawl in the server env. Other npm use may still hit EACCES until someone runs: sudo chown -R shyampatel ~/.npm
- Verified end-to-end from the CLI: firecrawl_scrape of https://members.poolerchamber.com/eventcalendar returned the full page as markdown (about 32k chars).
- Note: in headless -p runs the tool needed --allowedTools mcp__firecrawl__firecrawl_scrape; interactive sessions will simply ask Shyam to approve the tool the first time.
