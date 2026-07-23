---
name: Run a Confirmation of Payee check
description: Verify a payee's name against their account details (outbound CoP) before paying, to reduce APP fraud.
api: openapi/clearbank-cop-outbound-v1.json
operations: []
---

# Run a Confirmation of Payee (CoP) check

ClearBank's outbound Confirmation of Payee implements the Pay.UK CoP standard.

## Auth (every request)
- `Authorization: Bearer <API token>`, an RSA `DigitalSignature` over the body, and a unique `X-Request-Id`.

## Steps
1. **Optional — validate the account routing (SRD)** — `POST /open-banking/outbound/v1/srd/validate` to check the sort code / account is reachable for CoP.
   - `200` on success; `400` validation; `403` not permitted.
2. **Verify the payee name** — `POST /open-banking/outbound/v1/name-verification` with the payee's account identifier and the name to check.
   - `200` returns a match / close-match / no-match result.
   - `422` = CoP participant not found; `424` = the downstream CoP participant errored; `400`/`403` as above.
3. **Decide** — proceed to initiate the payment (FPS/CHAPS) on a match; warn or block on a no-match / close-match per your fraud policy.

## Rules
- These operations carry no `operationId` in the published spec — bind by method + path (`POST /open-banking/outbound/v1/name-verification`, `POST /open-banking/outbound/v1/srd/validate`).
- Errors follow RFC 7807 `ProblemDetails`.
