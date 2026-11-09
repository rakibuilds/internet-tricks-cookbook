# Contributing

Thanks for helping keep this cookbook useful. Tricks go stale as platforms change, so fixes and updates matter as much as new recipes.

## Repository Structure

This tree is generated automatically by `scripts/build_index.py`.

<!-- TREE:START -->
```text
internet-tricks-cookbook/
|-- .github/
|   `-- workflows/
|       `-- index-check.yml
|-- api-and-webhooks/
|   |-- dynamic-dns-updater.py
|   |-- README.md
|   `-- status-check-webhook.sh
|-- assets/
|   `-- logo.svg
|-- automation/
|   |-- headless-scraper.js
|   |-- README.md
|   `-- rss-feed-generator.py
|-- browser-and-search/
|   |-- advanced-search-operators.txt
|   |-- hidden-flags-config.txt
|   `-- README.md
|-- browsers/
|   |-- chrome/
|   |   |-- custom-search-shortcuts.md
|   |   `-- keyboard-shortcuts.md
|   |-- firefox/
|   |   |-- about-pages.md
|   |   `-- containers-and-reader-view.md
|   |-- general/
|   |   `-- hidden-flags-config.txt
|   |-- search/
|   |   |-- advanced-search-operators.txt
|   |   `-- quick-answers.md
|   `-- README.md
|-- developer/
|   |-- api-and-webhooks/
|   |   |-- curl-cheatsheet.md
|   |   |-- dynamic-dns-updater.py
|   |   `-- status-check-webhook.sh
|   |-- automation/
|   |   |-- headless-scraper.js
|   |   `-- rss-feed-generator.py
|   |-- devtools/
|   |   |-- devtools-console-tricks.md
|   |   |-- network-throttling-profiles.json
|   |   `-- shortcuts-and-commands.md
|   |-- git-and-github/
|   |   |-- fork-and-sync-upstream.md
|   |   |-- git-undo-cheatsheet.md
|   |   `-- github-shortcuts.md
|   `-- README.md
|-- devtools/
|   |-- devtools-console-tricks.md
|   |-- network-throttling-profiles.json
|   `-- README.md
|-- everyday/
|   |-- google-maps-offline.md
|   |-- price-comparison-tips.md
|   |-- README.md
|   `-- windows-shortcuts.md
|-- everyday-savings/
|   |-- price-comparison-tips.md
|   `-- README.md
|-- privacy-and-accounts/
|   |-- disposable-email-routing.md
|   |-- README.md
|   `-- remove-tracking-parameters.md
|-- privacy-and-security/
|   |-- check-data-breaches.md
|   |-- disposable-email-routing.md
|   |-- README.md
|   |-- remove-tracking-parameters.md
|   |-- review-app-permissions.md
|   |-- spot-phishing-links.md
|   |-- strong-passwords-and-passkeys.md
|   `-- two-factor-authentication.md
|-- scripts/
|   `-- build_index.py
|-- social-and-content/
|   |-- clean-video-sharing.md
|   |-- feed-algorithm-resets.md
|   `-- README.md
|-- social-media/
|   |-- facebook/
|   |   |-- feed-controls.md
|   |   `-- privacy-checkup.md
|   |-- general/
|   |   |-- clean-video-sharing.md
|   |   |-- download-your-data.md
|   |   `-- feed-algorithm-resets.md
|   |-- instagram/
|   |   |-- control-your-feed.md
|   |   `-- privacy-and-safety-settings.md
|   |-- linkedin/
|   |   `-- search-and-privacy.md
|   |-- reddit/
|   |   `-- search-and-feeds.md
|   |-- tiktok/
|   |   `-- content-controls.md
|   |-- whatsapp/
|   |   |-- handy-features.md
|   |   |-- privacy-settings.md
|   |   `-- text-formatting.md
|   |-- x-twitter/
|   |   |-- mute-and-filter.md
|   |   `-- search-operators.md
|   |-- youtube/
|   |   |-- keyboard-shortcuts.md
|   |   `-- playback-controls.md
|   `-- README.md
|-- .gitattributes
|-- .gitignore
|-- CONTRIBUTING.md
|-- LICENSE
|-- README.md
`-- RECIPE_TEMPLATE.md
```
<!-- TREE:END -->

## Where Does a Trick Go?

| Your trick is about | Put it in |
|---|---|
| A social platform (YouTube, Instagram, WhatsApp, and so on) | `social-media/<platform>/` |
| A tip that applies to several platforms | `social-media/general/` |
| A web browser or web search | `browsers/<browser or search>/` |
| Passwords, accounts, scams, tracking | `privacy-and-security/` |
| Code, DevTools, scripts, APIs, Git | `developer/<topic>/` |
| Anything else useful in daily life | `everyday/` |

A new platform or topic only needs a new folder. Create it, add your recipe, and run the index script. A brand new top-level section also works. It shows up automatically, and you can give it a nicer title and badge in the `SECTIONS` list at the top of `scripts/build_index.py`.

## Adding a Trick

1. [Fork the repository](https://github.com/rakibuilds/internet-tricks-cookbook/fork) and clone your fork.
2. Create a branch: `git checkout -b trick/your-trick-name`
3. Copy [`RECIPE_TEMPLATE.md`](RECIPE_TEMPLATE.md) into the right folder and fill it in.
4. Run `python scripts/build_index.py` to update the README and section indexes.
5. Commit, push, and [open a Pull Request](https://github.com/rakibuilds/internet-tricks-cookbook/compare) describing the problem your trick solves.

## Recipe Format

Every recipe starts with a short header. The `Purpose` line is required because it becomes the description in the indexes.

- **Purpose:** one sentence on the problem it solves.
- **Requirements:** browser, tool, or account needed (or "None").
- **Steps or usage:** clear instructions anyone can follow.

Guides use Markdown (`.md`) or plain text (`.txt`). Scripts use their native extension (`.js`, `.py`, `.sh`) with the header written as a comment at the top. JSON files use a `"_purpose"` key. Use lowercase file names with hyphens, such as `my-new-trick.md`.

## Rules

Allowed:
- Browser and app settings, UI tweaks, and hidden toggles
- Privacy and tracking-reduction techniques
- Search shortcuts and productivity workflows
- Automation scripts, API recipes, and DevTools snippets

Not allowed:
- Account hijacking, credential harvesting, or phishing tools
- Malware, exploits, or anything designed to cause harm
- Bypassing paywalls, licensing, or access controls on content you have no right to access
- Anything that violates the law or harms others

Scripts that fetch web pages must respect `robots.txt`, rate limits, and site terms of service.

## Security

Never commit passwords, API tokens, or keys. Read credentials from environment variables, as `dynamic-dns-updater.py` does.

## Fixing Outdated Recipes

If a menu moved or a setting changed, edit the recipe and note the version or date you tested it on. You can also [open an issue](https://github.com/rakibuilds/internet-tricks-cookbook/issues/new) to report a broken recipe.
