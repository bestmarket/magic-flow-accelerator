# Import "Genie Buddy Pal" from GitHub

The repository is public and already cloned. It is itself a Lovable project export built on the exact same stack as this project, so the import is a direct code transfer — much faster than a cross-platform rebuild.

## What the app is
A YouTube content-strategy app: sign in, connect channels/sources, brainstorm ideas in a guided AI chat, and turn them into scripts and videos in a studio.

## Steps

1. **Enable Lovable Cloud** — the app needs login, a database, and storage, all of which Cloud provides with zero setup.

2. **Copy the code in**
   - All pages and components: home, auth, and the signed-in app (chat, channels, sources, studio).
   - Server logic: AI chat helpers (uses Lovable's built-in AI — no keys to provide), channel analysis, studio/video functions, and a scheduled-videos webhook endpoint.
   - UI components, hooks, styles, and public assets.

3. **Apply the database setup**
   - Run the 10 included database migrations (profiles, projects, sources, ideas, scripts, videos, channels, posts, cron config, source videos — plus the storage bucket and access rules).
   - Fix any drift between the included drizzle and Supabase migration sets; the Supabase set is authoritative.

4. **Install dependencies and verify**
   - Merge its package list, install, and confirm the build passes.
   - Open the preview and check the home page, sign-in page, and signed-in pages load.
   - Sign-in can't be fully verified until a real account signs up once in the preview (the source project's roadmap notes the same blocker).

5. **Handoff — existing data**
   - The repository contains no exported user data, so the preview will start empty. If the original app has real data (channels, scripts, videos), ask for CSV/JSON exports from its database dashboard afterward — or skip and start fresh.

## Technical details
- Same framework (TanStack Start) on both sides — no rewrite, files copy across nearly as-is.
- No external secrets required: AI runs through Lovable's built-in AI gateway, auth and database through Lovable Cloud. The only env var found (`LOVABLE_DB_MIGRATION_URL`, used by its drizzle config) is a leftover dev tool and will not be ported.
- The `drizzle/` config folder is dropped; database management happens through Cloud migrations.
