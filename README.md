# strings-fixture

A tiny throwaway repo for testing the Strings translation manager's pull/sync loop.

- `crowdin.yml` — points Strings at the base + locale files.
- `src/locales/en.json` — base/source strings (English).
- `src/locales/{fr,nl,de}.json` — partial translations (FR ~100%, NL ~78%, DE ~67%)
  so the New / Source-changed / Translated states all appear.

Strings only ever writes to a derived `l10n/<branch>` branch (locale files only).
This base file and the `main` branch are never edited by the platform.
