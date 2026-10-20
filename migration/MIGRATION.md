# Migration details

## Architecture and dependency inventory

| Component | Current implementation | Migration action |
| --- | --- | --- |
| Frontend | Hand-authored HTML, CSS, vanilla JavaScript in `dist/` | Serve these exact files. |
| Design and motion | Locally hosted Manrope and Barlow Condensed fonts, CSS breakpoints, hover transitions, smooth anchors, native dialogs, reduced-motion rules | Already included; no design rebuild needed. |
| Photos and icons | Two local JPEGs, local SVG favicon, inline SVG icons | Already included. |
| Backend / serverless functions | None | No backend migration. |
| Database / schemas / migrations | None; hosting manifest has no D1 or R2 bindings | No database files or customer data exist to export. |
| Visit planner | Client-side form validation and in-memory notes; cleared when dialog closes | Works unchanged. It does not send requests or reserve appointments. |
| Visitor authentication | None; website audience is public | Keep your new host public; no OAuth provider required. |
| Sites management authentication | Platform-managed admin authentication; platform metadata has an auth client but frontend never uses it | Use your new hosting dashboard’s access controls. Do not copy ChatGPT account credentials. |
| API / connector / AI dependencies | None; no fetch calls or SDK | No keys or replacement API services required. |
| Google reviews | Five manually transcribed reviews embedded in HTML, plus a dated 4.8/41 rating | No Google API or widget; future review updates are manual. |
| Directions / read reviews | Ordinary external Google Maps links | Retain links. Google is needed only when visitors follow them. |
| Telephone | `tel:+13106919772` | Retain; opens the visitor’s phone/calling app. |
| Clipboard | Browser Clipboard API with legacy fallback | Use HTTPS (or localhost for development). Browser restrictions can affect copying. |
| Fonts | Eight `.ttf` files and local `fonts.css` | No live Google Fonts connection needed. |
| Analytics / cookies / storage | No application analytics scripts, cookies, localStorage or sessionStorage | Nothing to migrate. Host access logs are separate. |
| Schedules / background tasks | None returned by the Site metadata | Nothing to migrate. |
| Package dependencies | None; no package.json, lockfile or node_modules in original project | Do not invent a dependency installation step. |
| Build system | None | Publish static files directly. |
| Hosting declaration | `.openai/hosting.json` identifies this Sites project and `dist` | Retain for archival provenance; independent hosts do not consume it. |
| Site source repository | Source snapshot preserved here | Create your own Git repository if desired. Git history and remote credentials are not required to run this snapshot. |
| Platform domain/CDN/TLS | ChatGPT Sites supplies the live URL, asset delivery and certificates | Your host must provide a new URL, HTTPS and domain connection. The chatgpt.site hostname is not transferable. |

## URLs to change in a migration working copy

Current live URL reported by the platform on October 13, 2026:
`https://rkmuffler.jkalka28227.chatgpt.site`

The original HTML still contains the earlier hostname `https://rk-muffler.jkalka28227.chatgpt.site`. This metadata mismatch was preserved because the user requested an exact source export and no live changes.

Once your independent origin is known, replace that older origin in `original-source/dist/index.html` in these four places:

1. `og:url`
2. `og:image` (keep `/assets/hero.jpg`)
3. Canonical URL
4. JSON-LD business `url`

These are metadata references, not application API calls. No JavaScript, font or image download depends on ChatGPT at runtime once static files are served from your host. Root-relative asset paths mean the website should be hosted at `/`, not a subfolder, unless you deliberately adapt the paths.

## Configuration templates

The files in `config-templates/` are newly authored, optional examples. They are not original production configuration and were not deployed or validated against an external host.

- `hosting-settings.example.json`: provider-neutral settings to enter in your host’s UI; not an executable provider configuration.
- `nginx.conf.example`: minimal static-file server block for a self-managed server. Replace the domain and directory; provision HTTPS separately before public launch. Host installations may need their own include/layout adjustments.
- `.env.example`: states that no environment variables are required. The app does not read `.env` files.

No deployment costs, accounts, DNS changes or purchases were initiated.

## Handoff check

After serving the unchanged files, check the hero, fonts, images, three service dialogs, mobile navigation, FAQs, five reviews, weekly hours, call links, Google Maps directions, visit planner validation, copy buttons, privacy dialog and reduced-motion behavior. Try both desktop and a narrow phone viewport. Confirm planner close resets its fields. Ensure forms do not claim to submit a booking.

Check that requests for `/app.js`, `/styles.css`, `/assets/fonts.css`, both photos and all fonts return their actual files, not a host’s fallback HTML page.

## Original documentation caveat

The original README is retained unchanged, including historical notes superseded by its final review update. Its phrase “Interactive behavior checked with a DOM harness where available” is not evidence of a completed browser or DOM-harness test. This export verifies source integrity and static references; it does not claim that such a test was performed.

## Assets and rights

The original README records the two Unsplash photo URLs and font names. These are illustrative photos, not images of the business. Reviewer text comes from the user’s Google screenshots and is static. Separate font license files and photo license certificates were not present in the original repository; no such originals have been invented or claimed to be exported. Asset authors retain applicable rights.

## Not exportable as application source

OpenAI’s proprietary platform services, platform authentication internals, infrastructure code, hosted certificates, backend deployment tools and dashboard implementation are not exposed in this project and are not included. Internal platform logs and account-level metadata are not included. None of those is required by the exported frontend. No app code, runtime asset, database or backend has been reconstructed to stand in for unavailable originals.
