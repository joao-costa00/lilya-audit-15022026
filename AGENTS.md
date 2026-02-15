# PROJECT KNOWLEDGE BASE

**Generated:** 2026-02-15 19:34 Europe/Lisbon
**Commit:** b8529fb
**Branch:** main

## OVERVIEW
Lilya is a Python ASGI toolkit/framework with a CLI and rich routing, middleware, and OpenAPI support. Tooling uses Hatch, Ruff, Mypy, and Pytest.

## STRUCTURE
```
lilya-audit-15022026/
├── lilya/           # Core framework code
├── tests/           # Pytest suite
├── docs_src/        # Docs examples/source code
├── docs/            # Documentation content (en/pt)
├── scripts/         # Dev/docs helper scripts
├── .github/         # CI workflows and templates
├── .spec-workflow/  # Spec workflow templates
├── pyproject.toml   # Tooling + packaging config
└── Taskfile.yaml    # Task runner shortcuts
```

## WHERE TO LOOK
| Task | Location | Notes |
|------|----------|-------|
| Routing | lilya/routing.py | Core routing/dispatch; large file |
| App bootstrap | lilya/apps.py | App class and integration |
| Responses | lilya/responses.py | Response classes, streaming, encoders |
| Dependency injection | lilya/dependencies.py | Provide/scoping/lifecycle |
| Middleware | lilya/middleware/ | DefineMiddleware + concrete middleware |
| OpenAPI | lilya/contrib/openapi/ | OpenAPIConfig, decorator, docs UI |
| Security | lilya/contrib/security/ | Security schemes, JWT, CSRF |
| CLI | lilya/cli/ | Directives, runserver, scaffolds |
| Templates | lilya/_internal/_templates/ | Project/app/deployment templates |
| Docs examples | docs_src/ | Runnable examples by topic |
| Tests | tests/ | Feature-area tests; async + anyio |

## CODE MAP
LSP unavailable (basedpyright not installed). Skipped.

## CONVENTIONS
- Python package-at-root layout: `lilya/` is the main package.
- Ruff line-length = 99; docs_src is excluded from Ruff (pyproject.toml).
- Mypy runs in strict mode with explicit overrides (pyproject.toml).
- Pre-commit runs ruff-check with `--fix` and ruff-format (.pre-commit-config.yaml).
- CLI entry point: `lilya = lilya.__main__:run_cli` (pyproject.toml).

## ANTI-PATTERNS (THIS PROJECT)
- Include routes **DO NOT** take path parameters (docs/en/docs/routing.md).

## UNIQUE STYLES
- Extensive use of examples under docs_src/ for documentation.
- Internal scaffolding templates live under lilya/_internal/_templates/.

## COMMANDS
```bash
# Lint/format/type checks
hatch fmt --check
hatch run test:check_types

# Tests
hatch run test:test

# Docs (uses scripts/docs.py)
hatch run docs:build
```

## NOTES
- Docs build uses scripts/docs.py and mkdocs configs under docs/en/.
- Test env may require external services (pyproject: test script notes docker services).
- Cache tests expect Redis (tests/caches/conftest.py).
- EditorConfig for .py allows max 120 chars; Ruff enforces 99.
