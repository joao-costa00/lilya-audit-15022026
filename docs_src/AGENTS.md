# PROJECT KNOWLEDGE BASE: docs_src/

## OVERVIEW
Runnable documentation examples organized by topic for MkDocs builds.

## STRUCTURE
- `applications/`     App initialization and settings examples.
- `background_tasks/` Background task examples.
- `controllers/`     Controller patterns.
- `middleware/`      Middleware examples.
- `openapi/`         OpenAPI config/examples.
- `responses/`       Response and encoding examples.
- `routing/`         Routing and include patterns.
- `security/`        Auth/JWT/CSRF examples.
- `requests/`        Request lifecycle examples.
- `websockets/`      WebSocket examples.

## WHERE TO LOOK
| Feature | Location | Notes |
|---------|----------|-------|
| OpenAPI | `openapi/` | config_usage, request/response bodies |
| Routing | `routing/` | include patterns + nested apps |
| Middleware | `middleware/` | built-in middleware usage |
| Security | `security/` | auth flows + hashing |
| Responses | `responses/` | encoders and response types |
| Settings | `applications/settings/` | settings_config examples |

## CONVENTIONS
- Examples are runnable Python files; minimal dependencies.
- Directory names mirror documentation topics.
- `docs_src/` is excluded from Ruff (pyproject.toml).

## ANTI-PATTERNS
None noted.
