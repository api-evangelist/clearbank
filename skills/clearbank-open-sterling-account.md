---
name: Open a ClearBank sterling account
description: Create a new GBP (sterling) account for an onboarded financial institution on ClearBank.
api: openapi/clearbank-sterling-v4.json
operations: [V4InstitutionsByInstitutionIdAccountsPost]
---

# Open a ClearBank sterling account

Use the ClearBank Financial Institutions API to open a sterling account under an institution.

## Auth (every request)
- Send `Authorization: Bearer <API token>` (generated in the ClearBank Portal against your CSR).
- Compute an RSA-SHA256 (PKCS#1 v1.5) signature of the raw request body and send it in the `DigitalSignature` header.
- Send a unique `X-Request-Id` (max 83 chars) — this is the idempotency key.

## Steps
1. **Create the account** — `POST /v4/Accounts` (`V4InstitutionsByInstitutionIdAccountsPost`) with the account owner/label payload for the target institution.
   - Success is `201 Created`.
   - `400` = validation error or missing/invalid `X-Request-Id`; `403` = not permitted for that institution; `409` = duplicate `X-Request-Id` within the 24h window.
2. **Wait for the webhook** — the account lifecycle is confirmed asynchronously via the `AccountCreated` webhook. Verify ClearBank's signature and reply `200` within 5 seconds echoing the `Nonce`, signed with your `DigitalSignature`.

## Rules
- Test against the simulation host `https://institution-api-sim.clearbank.co.uk` before production `https://institution-api.clearbank.co.uk`.
- Never reuse an `X-Request-Id`; a duplicate returns `409`.
- Errors follow RFC 7807 `ProblemDetails` (`type`/`title`/`status`/`detail`).
