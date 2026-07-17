# strings-fixture

A throwaway repo for testing the Strings translation manager's pull/sync loop —
now loaded with **real, at-scale** translation data (ring-twice mobile app) to
prove the platform handles a production-sized project.

- `crowdin.yml` — FR-base config: source `src/translates/fr.json`, translations
  `src/translates/__translations__/%locale%.json`.
- `src/translates/fr.json` — base/source strings (French), **3,391 keys**.
- `src/translates/__translations__/{fr-BE,fr-FR,nl-BE}.json` — the target-locale
  files (~3,392 keys each) → ~10k translation rows.

The content is public-facing ring-twice UI copy (the same strings shipped in the
app); it was screened for secrets/PII before publishing. Each source file's
original top-level locale wrapper (`{ "fr": … }`) was stripped so the base and
translation key paths align 1:1 — the Crowdin source/translation contract Strings
consumes.

Strings only ever writes to a derived `l10n/<branch>` branch (locale files only).
This base file and the `main` branch are never edited by the platform.
