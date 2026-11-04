# Standards: every repo looks good and stays current

Every repository in GPT-Hub-Community meets these rules. A pull request that breaks one isn't merged. Each repo checks them with `tools/readme_check.py`, run from its `tools/check.sh`.

## Looks

- **Banner:** `assets/banner-dark.svg` and `assets/banner-light.svg`, 1280×320, made from the shared template (`assets/` here). Kicker `GPT HUB COMMUNITY`, the name, a one-line pitch. Shown with `<picture>` so it matches light and dark mode.
- **Logo:** `assets/logo.svg`, hand-written on a square viewBox: the house tile (a rounded `151517` square with a `2e2e34` edge) and one blue `1667d9` symbol for what the repo does. No text inside. `assets/logo.png` is 512×512 rendered from it, and `assets/social-preview.png` is 1280×640 (logo, name and a one-line pitch, dark like the banner). A banner's logo is copied from `assets/logo.svg`, so the two match. The logo, or the banner that holds it, is shown at the top of the README.
- **Social preview:** the API can't set it. When it changes, the owner uploads `assets/social-preview.png` in the repo's Settings.
- **Badges:** one row under the banner: platform, language, status, version. Flat-square style, gray `3f3f46`, blue `1667d9` for status.
- **README order:** banner, badges, a one-paragraph pitch, then `## Access and contributing`, `Requirements`, `Setup`, `Usage`, `Testing`, `Project layout`, `Platform and device support`, `License`.
- **Short README:** at most 200 lines. Details go in `docs/`.
- **Repo settings:** description of at most 100 characters, topics (`gpt-hub` plus the platform and language), squash merge only, branches deleted on merge, no wiki or projects.

## Scripts

- **A TUI:** every script starts in a terminal UI that shows, in plain words, which phone it's using, what it's doing, progress (levels, time) and any problem with what to do about it. Raw logs stay behind a flag.
- **A screenshot of the TUI:** `assets/tui.png`, shown in `## Usage`, retaken whenever the TUI changes.
- **Every phone:** iPhone scripts work on every iPhone size (SE to Pro Max); Android scripts on short and tall screens. `## Platform and device support` lists the phones actually verified.
- **One command to start:** `start.sh` / `start.bat` (or `uv run <name>`), with setup steps that check for what's missing.

## Staying current

- **Same pull request:** a change to behavior, setup, commands or the TUI updates the README (and `assets/tui.png`) in that pull request.
- **Changelog:** every version bump adds `## <version> (<date>)` to `CHANGELOG.md`, newest first, written for users.
- **Versions match:** the version badge, `pyproject.toml` and the changelog say the same version.
- **No dead links:** relative links in the README must exist (checked).
- **Listed and linked:** every repo has a linked row in the org profile (`profile/README.md`), added in the pull request that creates or moves it, with its logo at 28 px. Images of private repos don't load on the public profile, so the row logo is a copy in this repo's `assets/logos/<repo>.svg`, updated whenever the repo's logo changes.
- **Monthly sweep:** maintainers check each repo's README, screenshots, topics and changelog against what the code does now.
