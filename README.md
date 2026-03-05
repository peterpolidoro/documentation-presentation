# GitHub Pages talk template: “Documentation as a Deliverable”

This repo is a **starter template** for publishing a short talk as a **series of web pages** using **GitHub Pages**.

The core idea is also the message of the talk:
- keep documentation in **open, durable formats** (Markdown, CSV, SVG, PDF/A, STEP, etc.)
- so it stays readable without buying a license, and stays usable years later.

## Quick start (no command line required)

1. Create a new repo on GitHub (or use this template).
2. Put the website content in the `docs/` folder (already done here).
3. In your repo: **Settings → Pages**
   - **Source:** Deploy from a branch
   - **Branch:** `main`
   - **Folder:** `/docs`
4. Wait for GitHub Pages to publish, then open the site URL shown in Settings → Pages.

GitHub’s official docs on publishing sources:
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Edit content

- Edit any file in `docs/` directly in the GitHub web UI.
- These pages are plain text **Markdown** (`.md`), plus a small `_config.yml`.

## Add images

Drop images in:
- `docs/assets/images/`

Then reference them in Markdown like:
```md
![alt text]({{ '/assets/images/my_photo.jpg' | relative_url }})
```

## License (optional)

If you want others to reuse the talk, consider adding a Creative Commons license, e.g. CC BY 4.0.
