# Humainum Docs (Mintlify)

The content and config for Humainum's documentation site, built for [Mintlify](https://mintlify.com). Its own repository — separate from `ai-webapp-builder-frontend` — so Mintlify's auto-deploy only ever watches this repo, not the whole app's history, and access to one can be granted without the other.

## What's already done

Every `.mdx` page states a fact that's already true and published elsewhere on [humainum.com](https://humainum.com) (the landing pages, the FAQ, the module data) — nothing invented for this site. `modules/overview.mdx` is a snapshot of the real module list at the time it was written; check the [live Toolbox](https://humainum.com/modules) for current status.

- `docs.json` — navigation, Humainum's real brand blue, logo, favicon
- `index.mdx`, `getting-started.mdx`, `the-agent.mdx`, `expert-network.mdx`, `native-mobile-apps.mdx`, `ownership-and-security.mdx`, `pricing-and-credits.mdx`, `faq.mdx`, `modules/overview.mdx`

## Publishing this repo to GitHub

This folder is a local git repo (not yet pushed anywhere). To get it onto GitHub:

```bash
# from inside this folder
gh repo create innoqa-docs --private --source=. --remote=origin --push
```

(`gh` is GitHub's own CLI — install it or use github.com's "New repository" button instead if you don't have it, then `git remote add origin <url>` and `git push -u origin main`.)

## Connecting it to Mintlify

1. Go to [mintlify.com](https://mintlify.com) and sign up (or log in) with the GitHub account/org this repo lives under.
2. In the Mintlify dashboard, create a new docs project and point it at **this** repository (`innoqa-docs`) — the docs root is the repo root here, since nothing else shares this repo.
3. Mintlify auto-deploys on every push to the connected branch — no separate build step to run.
4. You'll get a `<something>.mintlify.app` URL immediately. A custom domain (e.g. `docs.humainum.com`) is set from the same dashboard once you're ready — Settings → Domain.

## Local preview (no account needed)

```bash
npx mint dev
```

Run from this folder. Opens a local preview at `http://localhost:3000` so you can see changes before pushing.
