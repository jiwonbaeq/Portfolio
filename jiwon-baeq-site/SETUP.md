# Jiwon Baeq — portfolio site

Everything is free: GitHub stores the site, Netlify hosts it, and the editing panel runs at `/admin`.

## What's in this folder

| Path | What it is |
|---|---|
| `index.html` | The work grid |
| `contact.html` | The contact page |
| `data/projects.json` | Every project: name, client, agency, still, hover loop, Vimeo link. **Edited from /admin.** |
| `data/contact.json` | Portrait, bio, email, Instagram. **Edited from /admin.** |
| `media/` | Where uploaded stills and loops are stored |
| `admin/` | The editing panel (Sveltia CMS) |

## One-time setup (about 15 minutes)

1. **GitHub** — create a free account at github.com, then a new repository (name it anything, e.g. `portfolio`; keep it private if you like). Upload this whole folder to it, keeping the structure.
2. **Edit `admin/config.yml`** — replace `YOUR-GITHUB-USERNAME/YOUR-REPO-NAME` with your actual username and repo name. You can do this right in GitHub's web editor.
3. **Netlify** — create a free account at netlify.com → *Add new site* → *Import an existing project* → pick GitHub and select your repo. Leave build settings empty (there's no build step). Deploy. Netlify gives you a URL like `something.netlify.app`; paste it into the `site_url` line of `admin/config.yml`.
4. **Sign-in for the editor** — in Netlify: *Site configuration → Access & security → OAuth → Install provider → GitHub*. Netlify walks you through creating a GitHub OAuth app (two copy-pastes). This lets you sign in to `/admin` with your GitHub account.
   - Shortcut if that feels fiddly: skip it and instead sign in to `/admin` with a GitHub personal access token (GitHub → Settings → Developer settings → Fine-grained tokens, give it *Contents: read & write* on your repo). Sveltia offers this option on its login screen.
5. **Custom domain** (optional) — Netlify → *Domain management* → add your domain and follow the DNS steps.

## Editing the site

Go to `yoursite.com/admin`.

- **Work grid** — each project has name, client, agency, static thumbnail, hover loop, and Vimeo link. Drag the handle on the left of a project to reorder; the first one is top-left on the site. Use *Add* / the trash icon to add or remove tiles. Press **Publish** — the live site updates in about 30 seconds.
- **Contact page** — portrait, bio (blank line between paragraphs), email, Instagram handle.

## Media guidelines

- **Static thumbnail** — JPG or WebP, ~800px wide. Export a frame from the loop.
- **Hover loop** — MP4 (H.264) or WebM, no audio, ~480px wide, 3–8 seconds, under 5 MB. In Premiere: export H.264, 480×270, ~1.5 Mbps, uncheck *Export Audio*.
- **Full video** — upload to Vimeo, then paste the Vimeo URL into the project. Private/unlisted links work.

## If you ever need to change the layout

Tile count per row is `--cols` at the top of `index.html`. Fonts, sizes, and colors are all in the `:root` and header blocks at the top of each HTML file.
