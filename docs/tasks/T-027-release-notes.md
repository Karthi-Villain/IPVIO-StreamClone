# T-027 Release notes for every release

## Goal

Maintainer feedback (12 Nov 2026): GitHub releases have no proper release notes. The assistant must write them for every release from now on.

## Change

- `CLAUDE.md`: new section 16 "Releases and release notes" (rule for the assistant: close the CHANGELOG section, write `docs/release-notes/vX.Y.md`, propose the `update.json` notes line); section 13 lists the new folder.
- `docs/release-notes/TEMPLATE.md`: template (Highlights, New, Improved, Fixed, Good to know).
- `docs/release-notes/v1.4.1.md`: first notes, written from the CHANGELOG sections 1.4 and 1.4.1 (1.4 did not start for some users, so 1.4.1 lists both). Can be pasted into the existing GitHub release `v1.4.1`.
- `docs/RELEASE.md`, section 2 step 5: title format and where the notes come from.
- `CHANGELOG.md`: entry under Unreleased.

## Findings used

- `AppUpdate.kt`: the GitHub API fallback shows the first four non-empty lines of the release text that do not start with `#`, joined with " · ". The template puts four short highlights first.
- `Round17Logic.kt`: `update.json` `notes` is cut to 300 characters.

## Not changed

App code, `update.json` format, CI.

## Acceptance criteria

1. The next release prepared with the assistant contains `docs/release-notes/vX.Y.md` and a closed CHANGELOG section.
2. `v1.4.1.md` reads correctly when pasted into GitHub.

## Risks

None for users (documentation only). The 1.4.1 notes summarise the CHANGELOG; the maintainer should check them before pasting.

## Test results

Documentation only; no build or test needed. Nothing was run.

## Status

Done on branch `docs/T-027-release-notes`, PR #66 to `Emrodev/IPVIO-Stream` `main`.
