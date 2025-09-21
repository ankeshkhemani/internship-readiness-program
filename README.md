# 10 Week FastAPI Internship readiness program

### Week 1 — Python Core for Backend (typing, async, packaging, Git)

**Goals**: Write typed, idiomatic Python; use venv/poetry; async/await; clean project layout; Git workflow.
**Do**: Build a typed CLI “Tasker” with file/SQLite storage; publish README and a short DESIGN.md.
**Resources**:

* Pro Git (free online book). ([Git][1])
* Py logging cookbook for structured logs; use JSON logs. ([Python documentation][2])
* GitHub Skills (interactive). ([skills.github.com][3])
  **Pass bar**: All functions typed, tests pass locally, cohesive Git history (feature branches, PRs).

---

### Week 2 — SQL & Postgres + SQLAlchemy 2.0

**Goals**: Model schemas, write performant queries, use SQLAlchemy 2.0 style, transactions.
**Do**: Design an ERD for a “Blog+Auth” DB; implement CRUD with SQLAlchemy 2.0; basic indices.
**Resources**:

* SQLAlchemy Unified Tutorial (2.0 style). ([SQLAlchemy Documentation][4])
* Postgres tutorial (official). ([PostgreSQL][5])
  **Pass bar**: Migrations run clean; query uses `select()` 2.0 API; foreign keys + indexes explained.

---

### Week 3 — Web Basics & Testing Primer

**Goals**: HTTP/REST, status codes, auth concepts (JWT vs sessions), pytest fundamentals.
**Do**: Minimal Flask or Starlette service to internalize request/response; then add pytest.
**Resources**:

* pytest “Get Started” + how-tos. ([pytest][6])
* Starlette docs (FastAPI’s ASGI toolkit). ([Starlette][7])
  **Pass bar**: Unit + simple API tests (pytest) with clear fixtures.

---

### Week 4 — FastAPI Core I (routing, DI, Pydantic v2)

**Goals**: Build REST endpoints with validation and dependency injection; Pydantic v2 models.
**Do**: “Notes API” with CRUD, pagination, validation errors, OpenAPI docs.
**Resources**:

* FastAPI official tutorial: First Steps through Request Body. ([FastAPI][8])
* Pydantic v2 docs (models). ([Pydantic][9])
  **Pass bar**: Request/response models validated; automatic docs correct; 90% test coverage on routers.

---

### Week 5 — FastAPI Core II (Auth, Security)

**Goals**: OAuth2 Password flow, hashed passwords, JWT bearer, role-based access.
**Do**: Add `/auth/register`, `/auth/login`, refresh, protected routes; password hashing.
**Resources**:

* FastAPI “OAuth2 with Password + JWT” (canonical). ([FastAPI][10])
* TestDriven JWT in FastAPI (project-style). ([TestDriven.io][11])
  **Pass bar**: Tokens issued & verified; unauthorized requests blocked in tests.

---

### Week 6 — Persistence, Migrations, Testing Deep-Dive

**Goals**: SQLAlchemy 2.0 + Alembic migrations; httpx test client; async tests.
**Do**: Switch Notes/Auth app to Postgres; add Alembic; write httpx-based tests.
**Resources**:

* Alembic tutorial (official). ([alembic.sqlalchemy.org][12])
* FastAPI testing with httpx + async tests. ([FastAPI][13])
  **Pass bar**: `alembic upgrade head` on clean DB; CI runs unit + API tests.

---

### Week 7 — Capstone 1: Task Manager API (Multi-user)

**Goals**: Real project: JWT auth, users, tasks, labels; Postgres + Alembic; Dockerize.
**Do**: Ship a Dockerized service; add rate-limiting middleware; structured JSON logs.
**Resources**:

* Docker “Get Started” + beginner curriculum. ([Docker Documentation][14])
* SlowAPI for FastAPI/Starlette rate limiting. ([GitHub][15])
* Python structured logging best practices. ([New Relic][16])
  **Pass bar**: `docker compose up` works; rate limit test proves 429 path; logs machine-readable.

---

### Week 8 — Capstone 2: Mini E-commerce API (Async, Caching, Background Work)

**Goals**: Async endpoints, Redis caching, background tasks (email order confirmation).
**Do**: Products, cart, checkout; cache popular queries; send async confirmation.
**Resources**:

* FastAPI Background Tasks (official). ([FastAPI][17])
* Redis quick starts (official). ([Redis][18])
* Celery docs (for real task queue) vs in-process background tasks. ([Celery Documentation][19])
  **Pass bar**: Cache hit improves latency (demonstrate locally); background job executed reliably.

---

### Week 9 — Deployment, Observability & CI

**Goals**: Deploy one capstone to a free PaaS, add GitHub Actions CI, tune server workers.
**Do**: Deploy to Railway/Render/Fly.io; add CI: lint + test + build; gunicorn/uvicorn config.
**Resources**:

* Railway FastAPI guide / template. ([Railway Docs][20])
* Render FastAPI deploy guide. ([Render][21])
* Fly.io FastAPI guide. ([Fly][22])
* FastAPI “Server workers” & Uvicorn deployment notes. ([FastAPI][23])
* GitHub Actions for Python (official guide). ([GitHub Docs][24])
  **Pass bar**: Public URL live; PR triggers CI; simple load test shows stable concurrency.

---

### Week 10 — Security Hardening & Interview Prep

**Goals**: Apply OWASP API Top-10; add rate limiting, input validation, auth checks; polish portfolio; mock interviews.
**Do**: Security review + fixes; write SECURITY.md & POSTMORTEM.md (simulated incident).
**Resources**:

* OWASP API Security Top-10 (2023). ([OWASP][25])
  **Pass bar**: Documented mitigations for API1–API5 risks; two 45-min mock interviews passed.

---

## Daily cadence (Mon–Sun)

* **Mon–Thu (2–4h/day):** Learn + implement small slices + tests.
* **Fri (2h):** Refactor + write docs (README sections, decisions).
* **Sat (3h):** Milestone demo (record a 3–5 min Loom), open a PR, self-review against checklist.
* **Sun (2h):** Retrospective + write LinkedIn/GitHub summary post linking commits.

---

## Rubrics (use weekly)

* **Code quality**: Types present; modules cohesive; no dead code; clear naming.
* **Tests**: ≥80% coverage on core modules; fixtures for DB; httpx client used for API tests. ([FastAPI][13])
* **Security**: JWT verified; no secrets in repo; object-level auth enforced (e.g., users can’t access others’ records). ([OWASP][25])
* **Ops**: Docker runs locally; .env.sample provided; CI green on PR. ([Docker Documentation][14])
* **Docs**: README with quickstart + endpoints; DESIGN.md; SECURITY.md with OWASP mapping. ([OWASP][26])

---

## Portfolio checklist (what recruiters will look for)

* **Two solid FastAPI projects** with: Auth (JWT), Postgres + Alembic, tests, Docker, and **one live deployment** (Railway/Render/Fly). ([Railway Docs][20])
* **CI pipeline** (pytest + lint) visible in Actions. ([GitHub Docs][24])
* **Security notes** referencing OWASP API Top-10 mitigations. ([OWASP][25])
* **Short videos** demoing the API & code walkthrough (shows communication skills).
* **Issue tracker hygiene**: small issues, descriptive PRs, good commit messages.

---

## Starter tech decisions (so she doesn’t bikeshed)

* **Stack**: FastAPI + SQLAlchemy 2.0 + Alembic + Postgres + httpx + pytest. ([SQLAlchemy Documentation][4])
* **Auth**: OAuth2 password flow with JWT (FastAPI canonical example). ([FastAPI][10])
* **Rate limiting**: SlowAPI (or Redis-based custom limiter later). ([GitHub][15])
* **Background jobs**: Start with FastAPI BackgroundTasks; graduate to Celery + Redis if needed. ([FastAPI][17])
* **Deploy**: Pick one—Railway (fastest), Render (simple), or Fly.io (flexible). ([Railway Docs][20])

---

## “What to learn where” map (quick links)

* **FastAPI user guide** (full). ([FastAPI][8])
* **Pydantic v2** (models). ([Pydantic][27])
* **SQLAlchemy 2.0 unified tutorial**. ([SQLAlchemy Documentation][4])
* **Alembic tutorial**. ([alembic.sqlalchemy.org][12])
* **pytest quickstart**. ([pytest][6])
* **Testing FastAPI** (official). ([FastAPI][13])
* **Uvicorn/Gunicorn deployment notes**. ([uvicorn.org][28])
* **OWASP API Top-10 (2023)**. ([OWASP][26])
* **Docker getting started**. ([Docker Documentation][14])
* **Railway / Render / Fly deploy guides**. ([Railway Docs][20])

---

## Stretch (only if ahead)

* **Observability**: Add request IDs (starlette-context), structured logging policy. ([starlette-context.readthedocs.io][29])
* **HTTP clients**: Use httpx for external calls & timeouts/retries. ([python-httpx.org][30])
* **Security extras**: Rate limit auth endpoints; CSRF for cookie flows; audit sensitive logs. ([GitHub][15])

---

If you want, I can turn this into a **printable weekly checklist** (with tick-boxes for each deliverable and rubric item) and a **GitHub issue template** your niece can drop into each repo to guide her PRs.

[1]: https://git-scm.com/book/en/v2?utm_source=chatgpt.com "Pro Git book"
[2]: https://docs.python.org/3/howto/logging-cookbook.html?utm_source=chatgpt.com "Logging Cookbook — Python 3.13.7 documentation"
[3]: https://skills.github.com/?utm_source=chatgpt.com "GitHub Skills"
[4]: https://docs.sqlalchemy.org/tutorial/index.html?utm_source=chatgpt.com "SQLAlchemy Unified Tutorial"
[5]: https://www.postgresql.org/docs/current/tutorial.html?utm_source=chatgpt.com "Documentation: 17: Part I. Tutorial"
[6]: https://docs.pytest.org/en/stable/getting-started.html?utm_source=chatgpt.com "Get Started"
[7]: https://www.starlette.io/?utm_source=chatgpt.com "Starlette"
[8]: https://fastapi.tiangolo.com/tutorial/?utm_source=chatgpt.com "Tutorial - User Guide"
[9]: https://docs.pydantic.dev/latest/?utm_source=chatgpt.com "Welcome to Pydantic - Pydantic"
[10]: https://fastapi.tiangolo.com/tutorial/security/oauth2-jwt/?utm_source=chatgpt.com "OAuth2 with Password (and hashing), Bearer with JWT tokens"
[11]: https://testdriven.io/blog/fastapi-jwt-auth/?utm_source=chatgpt.com "Securing FastAPI with JWT Token-based Authentication | TestDriven.io"
[12]: https://alembic.sqlalchemy.org/en/latest/tutorial.html?utm_source=chatgpt.com "Tutorial — Alembic 1.16.5 documentation - SQLAlchemy"
[13]: https://fastapi.tiangolo.com/tutorial/testing/?utm_source=chatgpt.com "Testing"
[14]: https://docs.docker.com/get-started/?utm_source=chatgpt.com "Get started"
[15]: https://github.com/laurentS/slowapi?utm_source=chatgpt.com "laurentS/slowapi: A rate limiter for Starlette and FastAPI"
[16]: https://newrelic.com/blog/how-to-relic/python-structured-logging?utm_source=chatgpt.com "Guide to structured logging in Python"
[17]: https://fastapi.tiangolo.com/tutorial/background-tasks/?utm_source=chatgpt.com "Background Tasks"
[18]: https://redis.io/docs/latest/develop/get-started/?utm_source=chatgpt.com "Quick starts | Docs"
[19]: https://docs.celeryq.dev/?utm_source=chatgpt.com "Celery - Distributed Task Queue — Celery 5.5.3 documentation"
[20]: https://docs.railway.com/guides/fastapi?utm_source=chatgpt.com "Deploy a FastAPI App"
[21]: https://render.com/docs/deploy-fastapi?utm_source=chatgpt.com "Deploy a FastAPI App"
[22]: https://fly.io/docs/python/frameworks/fastapi/?utm_source=chatgpt.com "Run a FastAPI app · Fly Docs"
[23]: https://fastapi.tiangolo.com/deployment/server-workers/?utm_source=chatgpt.com "Server Workers - Uvicorn with Workers"
[24]: https://docs.github.com/actions/guides/building-and-testing-python?utm_source=chatgpt.com "Building and testing Python"
[25]: https://owasp.org/API-Security/editions/2023/en/0x11-t10/?utm_source=chatgpt.com "OWASP Top 10 API Security Risks – 2023"
[26]: https://owasp.org/API-Security/editions/2023/en/0x00-header/?utm_source=chatgpt.com "OWASP API Security Top 10 2023 edition"
[27]: https://docs.pydantic.dev/latest/concepts/models/?utm_source=chatgpt.com "Models"
[28]: https://www.uvicorn.org/deployment/?utm_source=chatgpt.com "Deployment"
[29]: https://starlette-context.readthedocs.io/?utm_source=chatgpt.com "starlette-context — starlette-context 0.4.0 documentation"
[30]: https://www.python-httpx.org/?utm_source=chatgpt.com "HTTPX"
