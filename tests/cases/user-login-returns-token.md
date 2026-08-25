---
id: user-login-returns-token
title: Registered user can log in and receives a JWT
preconditions:
  - API is reachable at the base URL (env: API_BASE_URL)
  - A registered user exists (credentials via env: AQ_API_USER / AQ_API_PASS — never literals)
steps:
  - action: POST /api/users/login with the user's email and password from env
    expected: 200 response with a user object containing a non-empty token
  - action: GET /api/user with the returned token in the Authorization header
    expected: 200 response echoing the same user's email
tags:
  - smoke
  - auth
  - api
target: api
priority: P0
---

Seeded AgentQA case for the pytest API sandbox (AQ-110). Parser lands in AQ-108.
