# CoC AI Manager

Private Clash of Clans player dashboard for #R22JJ2PG8.

## Project status
- Supabase project: coc-ai-manager (Mumbai, ap-south-1)
- Database schema: deployed with row-level security on player snapshots and upgrade tasks.
- Edge Function: coc-sync deployed with JWT verification enabled.
- Frontend source bundle: available as coc-ai-manager-source.zip in the project handoff.
- Six-hour scheduler: not yet enabled.
- Supercell API secret: must be configured by the owner after revoking the previously exposed token.

## Local setup
1. Unzip the supplied source bundle into this repository.
2. Copy .env.example to .env and set VITE_SUPABASE_URL and VITE_SUPABASE_ANON_KEY.
3. Install dependencies with npm install.
4. Run npm run build to verify, then npm run dev to preview.

## Secrets
Set SUPERCELL_COC_API_TOKEN only in Supabase Edge Function secrets. Never commit it or place it in a VITE_ variable.

## API constraints
The official Clash of Clans player API is read-only. It does not provide current resources, building levels, builder availability, upgrade timers, or in-game actions. The upgrade checklist is therefore a manual tracker, not an automated game controller.
