# PROJECT KNOWLEDGE BASE: tests/

## OVERVIEW
Pytest suite covering core framework behavior, CLI, and contrib modules.

## STRUCTURE
- `routing/`        Routing and URL reversing tests.
- `middleware/`     Middleware behavior and edge cases.
- `security/`       Security schemes, JWT, CSRF tests.
- `openapi/`        OpenAPI schema generation tests.
- `cli/`            CLI directive tests (Sayer-based).
- `caches/`         Memory/Redis cache tests.
- `contrib/`        Optional integrations (proxy, schedulers, cqrs).
- `templates/`      Template rendering tests.
- `params/`         Param parsing/validation.
- `dependencies/`   Dependency injection tests.
- `encoders/`       Encoder behavior tests.
- `permissions/`    Permission behavior tests.
- `lifespan/`       Lifespan/event tests.

## WHERE TO LOOK
| Task | Location | Notes |
|------|----------|-------|
| Global fixtures | `conftest.py` | `test_client_factory`, encoder registration |
| Cache fixtures | `caches/conftest.py` | sets `asyncio_mode = "auto"` |
| CLI fixtures | `cli/conftest.py` | SayerTestClient, event loop |
| Settings | `settings.py` | AppTestSettings for tests |
| Routing tests | `routing/` | large routing coverage |
| OpenAPI tests | `openapi/` | schema and controller tests |

## CONVENTIONS
- Async tests use anyio/pytest-asyncio; some suites rely on `asyncio_mode = auto`.
- Fixtures are layered with per-area `conftest.py` files.
- Many tests assume `LILYA_SETTINGS_MODULE=tests.settings.AppTestSettings`.

## ANTI-PATTERNS
None noted.
