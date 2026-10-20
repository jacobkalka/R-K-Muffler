# R & K Muffler — original source export

This ZIP contains all 17 tracked files from the original source of published version 3, including the website’s 15 public files. It is an export of the actual project, not a reconstruction. The five Google reviews and Monday–Friday 8 AM–5:30 PM hours are included.

**Nothing was changed or republished on the live website during this export.**

## What is original, and what is new?

- `original-source/` — unchanged files read directly from source commit `10fded9aa0a763bc0417d3bc5621245d3fa638ad`. This includes the original README and `.openai/hosting.json`.
- `migration/` — newly written setup instructions, hosting templates, and a Claude Code handoff. These are additions for portability, not claimed to be original source.
- `SOURCE-MANIFEST.json` — per-file SHA-256 hashes, sizes, and provenance.

Despite its `dist` directory name, this project’s HTML, CSS and JavaScript were authored directly there. There is no missing React/Vue application, build pipeline, minification stage or separate source map. These files are the original working source.

## Run it locally

Extract the ZIP. In a terminal, enter the extracted `rk-muffler-complete-source` folder and run:

```sh
python3 -m http.server 8080 --bind 127.0.0.1 --directory original-source/dist
```

On Windows with the Python launcher:

```powershell
py -m http.server 8080 --bind 127.0.0.1 --directory original-source/dist
```

Open `http://localhost:8080`. Stop the development server with Ctrl+C. Do not use this development server as public production hosting.

Serve `dist` as the web root. Double-clicking `index.html` is insufficient because stylesheet, font, script and photo paths begin with `/`.

No npm installation, API key, account, build step, or database setup is required. Python is only a convenient local web server; it is not an application dependency.

## Host independently

Use a host capable of serving static files. Upload the **contents of `original-source/dist/`** into its public web root. The public root must contain `index.html`, `app.js`, `styles.css`, and `assets/` together. Use HTTPS so clipboard features operate in a secure browser context.

For a repository-connected host: use `original-source` as the project directory, no build command, and `dist` as the publish directory. Alternatively set the repository root to this export and publish `original-source/dist`. Do not require a framework or serverless runtime.

Before launching your new domain, follow `migration/MIGRATION.md` to change four absolute SEO URLs in your copied HTML. The originals are intentionally unchanged here.

Open this folder with Claude Code and give it `migration/CLAUDE-HANDOFF.md`.

## Completeness and limits

All tracked application source and runtime assets are present. This site has no application backend, database schema, stored customer records, authentication, paid API integration, live reviews feed, online booking server, or environment variables to export. The visit planner only prepares call notes locally; appointments happen by telephone.

The proprietary ChatGPT Sites hosting platform, CDN/TLS/DNS machinery, management tools, internal logs and dashboard are not application source and are not included. Replace those with your host’s static hosting and domain configuration. They are not needed to run the exported site.

Editor conversation history, private account credentials, reference screenshots and temporary research files are not part of the working source and are not included. Every runtime photo, font, icon and review text used by the site is included.

The export was verified against the saved source version and original Git bytes. All local resource paths and JavaScript syntax were checked. Browser rendering and independent-host deployment were not performed during export. Identical source preserves the design and behaviors, but your new host and browser configuration must still be checked.
