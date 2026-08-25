---
id: article-crud-roundtrip
title: Authenticated user can create, read, and delete an article
preconditions:
  - API is reachable at the base URL (env: API_BASE_URL)
  - A valid auth token is available (obtained via login with env: AQ_API_USER / AQ_API_PASS)
steps:
  - action: POST /api/articles with title, description, and body
    expected: 201/200 response containing the article with a generated slug
  - action: GET /api/articles/{slug} for the returned slug
    expected: 200 response with the same title and body
  - action: DELETE /api/articles/{slug} with the auth token
    expected: 2xx response, and a subsequent GET of the slug returns 404
tags:
  - regression
  - articles
  - api
target: api
priority: P1
---

Seeded AgentQA case for the pytest API sandbox (AQ-110). Parser lands in AQ-108.
