# jlpt-bank

JLPT (Japanese-Language Proficiency Test) practice **question bank** consumed by my JLPT quiz Android app.

- All questions are **100% original** — emulating the JLPT format and difficulty but never copying any official past question.
- Levels included: **N5 / N4 / N3** (100 questions each, 5 categories: kanji reading, vocabulary-in-context, grammar form, sentence ordering ★, short reading).
- Explanation language: **English** (Vietnamese available for N5).
- Format: single JSON per release tag.

## Layout

```
version.json            # tiny manifest — always points to the latest release
v1.0.0/jlpt_all.json    # immutable, content-addressed by version tag
v1.1.0/...              # future releases append here
```

The app fetches `version.json` on launch, compares with its locally-cached version, and downloads the referenced bank JSON only when a newer version is available. If the network or this repo is unavailable, the app continues to work with its embedded bank.

## License

Question content is licensed under **CC BY-NC-SA 4.0** (see `LICENSE`).
You may share and adapt for non-commercial purposes with attribution and a compatible license. Commercial use is not granted by this license.

## Versioning

Bumped semantically when:

- patch: typo/translation fix
- minor: additional questions or translations
- major: schema change (e.g., new question type, new field)
