# Project Rules — LOT Dashboard

## Project Context
This is the Legend of Toys (LOT) operations system, built by the co-founder Afshaan. The system is built and maintained using the following workflow:

- **Claude Chat** acts as the orchestrator and designer — it handles strategy, system design, and produces specific change instructions for each component.
- **Four Claude Code agents** run in separate terminal tabs, each responsible for edits to files in their own folder/repo. This agent is one of those four.
- **Database edits** are handled directly by the co-founder based on instructions from Claude Chat — there is no separate agent for database interaction.
- Development happens across two laptops (office and home) with a similar setup on both.

The build comprises three separate but connected systems:

1. **Store system** (`legendlot/Stores`) — handles everything to do with store operations for Legend of Toys, including raw materials, procurement, POs, GRN receiving, inventory management, and issuing raw material to production.
2. **Production system** — contains two sub-systems:
   - **Scanner app** (`legendlot/production`) — used by people on the factory floor to scan inventory.
   - **Dashboard** (`legendlot/dashboard`) — used for reporting and general admin of the production system. **This agent is responsible for this system.**
3. **Cloudflare Worker** (`legendlot/Cloudfare`) — the single backend API layer that all three frontend systems route through to communicate with Supabase.

## Session Start
- Always run `git pull` from remote at the beginning of each session.

## File Editing
- Only edit `index.html`. No other files should be modified.
- If instructions reference changes to any other file, highlight them to the user and skip those edits.

## Git Workflow
- After making all changes, automatically commit and push to git.
- Any time local files are changed, commit and push to git.
- Do not ask for confirmation before committing and pushing — do it automatically.
