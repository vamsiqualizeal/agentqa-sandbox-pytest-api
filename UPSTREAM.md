# Upstream provenance (AQ-110)

| Field | Value |
| --- | --- |
| Source | https://github.com/nsidnev/fastapi-realworld-example-app |
| Commit | `029eb7781c60d5f563ee8990a0cbfb79b244538c` (branch `master` at pin; upstream archived 2022-08-21) |
| License | MIT (see `LICENSE`) |
| Vendored | 2026-08-25 as a pinned fork in `vamsiqualizeal/agentqa-sandbox-pytest-api` |

This tree is a **third-party brownfield** FastAPI + pytest API application we did
not author (a RealWorld-spec backend: users, auth, articles, comments; ~90
pytest tests; PostgreSQL via `docker-compose.yml`). The upstream is archived,
so this pin is stable by construction.

AgentQA additions in this tree are limited to:

- this `UPSTREAM.md`
- seeded AgentQA case files under `tests/cases/` (spec FR-1 shape)
- a one-line `Dockerfile` fix (poetry pinned to 1.1.15 — upstream's `poetry==1.1` resolves to a broken 1.1.0 on modern pip)

No OpenAPI document is committed in this repo — the API catalog must be built
from capture (AQ-210 acceptance).
Credentials must remain env/vault refs — never commit real secrets.
