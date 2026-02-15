# PROJECT KNOWLEDGE BASE: lilya/

## OVERVIEW
Core framework package for Lilya (ASGI toolkit).

## STRUCTURE
- `cli/`            CLI commands and directive loading.
- `conf/`           Settings defaults and config helpers.
- `contrib/`        Optional integrations (OpenAPI, security, proxy, etc.).
- `middleware/`     Built-in middleware implementations.
- `protocols/`      Protocols and interface contracts.
- `testclient/`     Test client implementation.
- `_internal/`      Private helpers and scaffolding templates.
- `templating/`     Template rendering helpers.
- `caches/`         Cache backends.
- `permissions/`    Permission protocols and utilities.
- `introspection/`  Introspection helpers.

## WHERE TO LOOK
| Task | Location | Notes |
|------|----------|-------|
| App bootstrap | `apps.py` | Lilya app class + router glue |
| Routing | `routing.py` | Core matching/dispatch (very large) |
| Responses | `responses.py` | Response classes, streaming |
| Handler binding | `_internal/_responses.py` | Signature/plan caching |
| Dependency injection | `dependencies.py` | Provide/scoping/lifecycle |
| Settings | `conf/global_settings.py` | Global settings model |
| Middleware base | `middleware/base.py` | DefineMiddleware wrapper |
| Middleware protocol | `protocols/middleware.py` | Middleware contract |
| OpenAPI | `contrib/openapi/` | OpenAPIConfig + decorator |
| Security | `contrib/security/` | JWT, CSRF, schemes |
| CLI | `cli/cli.py` | CLI entry + directives |
| Test client | `testclient/` | sync/async clients + transport |
| Templates | `_internal/_templates/` | Project/app/deploy templates |

## CONVENTIONS
- Public APIs live at top-level modules; `_internal/` is private.
- Middleware declared via `DefineMiddleware` and `MiddlewareProtocol`.
- CLI directives live under `cli/directives/operations/`.

## ANTI-PATTERNS
None noted.
