---
name: contabo-manage-instance-lifecycle
description: List, inspect and power-cycle Contabo compute instances through the Contabo API.
api: contabo:contabo-api
operations:
- retrieveInstancesList
- retrieveInstance
- start
- stop
- restart
- shutdown
generated: '2026-10-13'
method: generated
source: openapi/contabo-openapi.yml
---
1. Obtain a bearer token via the OAuth2 password grant at https://auth.contabo.com/auth/realms/contabo/protocol/openid-connect/token (ClientId, ClientSecret, API user, API password).
2. Call `retrieveInstancesList` (GET /v1/compute/instances) with `Authorization: Bearer` and an `x-request-id` UUID.
3. Call `retrieveInstance` for the chosen instanceId to read its status.
4. Use `start`, `stop`, `shutdown` or `restart` (POST /v1/compute/instances/{instanceId}/actions/...).
5. On 429 wait before retrying; no idempotency key is documented, so do not blindly repeat writes.
