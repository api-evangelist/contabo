---
name: contabo-snapshot-and-rollback
description: Take a snapshot of a Contabo instance and roll the instance back to it.
api: contabo:contabo-api
operations:
- createSnapshot
- retrieveSnapshotList
- retrieveSnapshot
- rollbackSnapshot
- deleteSnapshot
generated: '2026-10-13'
method: generated
source: openapi/contabo-openapi.yml
---
1. Authenticate as in the Getting Started section of https://api.contabo.com/ and send an `x-request-id` UUID per request.
2. `createSnapshot` (POST /v1/compute/instances/{instanceId}/snapshots) before a risky change.
3. `retrieveSnapshotList` / `retrieveSnapshot` to confirm it exists.
4. `rollbackSnapshot` to revert the instance; `deleteSnapshot` once it is no longer needed.
