# PROJECT KNOWLEDGE BASE: docs/

## OVERVIEW
Documentation content for Lilya (English + Portuguese) with MkDocs configs.

## STRUCTURE
```
docs/
├── en/                  # English docs project
│   ├── docs/            # Markdown content
│   └── mkdocs.yml       # MkDocs config
├── pt/                  # Portuguese docs project
│   ├── docs/            # Markdown content
│   └── mkdocs.yml       # MkDocs config
├── language_names.yml   # Language display names
└── missing-translation.md # Translation tracking
```

## WHERE TO LOOK
| Item | Location | Notes |
|------|----------|-------|
| English content | `en/docs/` | Primary documentation set |
| Portuguese content | `pt/docs/` | Translated documentation |
| English config | `en/mkdocs.yml` | Site config + nav |
| Portuguese config | `pt/mkdocs.yml` | PT site config |
| Language metadata | `language_names.yml` | Language labels |
| Translation status | `missing-translation.md` | Missing pages |

## CONVENTIONS
- Docs are stored per-language under `docs/en` and `docs/pt`.
- MkDocs configs live alongside their language content.

## ANTI-PATTERNS
None noted.
