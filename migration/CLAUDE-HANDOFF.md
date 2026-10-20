# Handoff for Claude Code

This is the original R & K Muffler static website, exported from ChatGPT Sites published version 3, commit `10fded9aa0a763bc0417d3bc5621245d3fa638ad`.

Read `START-HERE.md`, `migration/MIGRATION.md`, and `SOURCE-MANIFEST.json` first. `original-source/` contains the exact original files. Migration docs/templates are newly authored and separate.

My goal is to host and edit this website independently. Preserve the current design, layout, colors, font files, photos, copy, animations, breakpoints and functionality. Do not rebuild the site or convert frameworks. There is no missing backend/database/package manifest. Serve `original-source/dist` as the web root with no build step.

First preview locally and verify the original files against SOURCE-MANIFEST.json. Work on a copy or new Git branch for changes. When I provide an independent domain, update only the four old absolute origin references in `dist/index.html` as documented. Keep `tel:` and Google Maps links. Set up hosting appropriate to my chosen provider and test responsive layout, dialogs, navigation, FAQ, hours, reviews, call-note planner, clipboard and privacy text.

The planner prepares notes locally; it does not book or send messages. Do not invent a booking backend, claim requests are sent, or add authentication. There are no API keys or environment secrets to request for existing functionality.

Do not edit, redeploy, unpublish, alter access to, or change the domain/DNS of the existing ChatGPT Sites website. Independent migration and any later cutover should be handled separately under my instructions.
