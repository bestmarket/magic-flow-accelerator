# Roadmap

- [x] Import geniefriend-magic-flow from GitHub (code, Cloud, schema, storage bucket, auth providers, scheduler cron)
- [x] Verify build and pages load (home redirects to sign-in, auth page renders, no console errors)
- [ ] User sign-in verification — blocked: no auth user exists yet; user needs to sign up/sign in once in the preview
- [ ] Import existing data — blocked: no CSV/JSON record exports supplied from the original app's database
- [ ] Scheduler cron goes live on publish — the 15-min publishing job targets the stable production URL, which serves nothing until the app is published
