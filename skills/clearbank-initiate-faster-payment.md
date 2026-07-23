---
name: Initiate a UK Faster Payment
description: Send a UK Faster Payment (FPS) and handle its asynchronous settlement outcome on ClearBank.
api: openapi/clearbank-fps-initiate-payment-v3.json
operations: [Post, PostReturn]
---

# Initiate a UK Faster Payment (FPS)

## Auth (every request)
- `Authorization: Bearer <API token>`, an RSA `DigitalSignature` over the body, and a unique `X-Request-Id`.

## Steps
1. **Optional — Confirmation of Payee** — before paying a new payee, call `POST /open-banking/outbound/v1/name-verification` (Confirmation of Payee API, `openapi/clearbank-cop-outbound-v1.json`) to check the payee name matches the account.
2. **Initiate the payment** — `POST /v3/payments/fps` (`Post`) with the debtor account, creditor account identifier, amount and remittance info.
   - Returns `202 Accepted` — the payment is now in flight.
   - `400` = validation / bad `X-Request-Id`; `404` = account not found; `422` = business-rule rejection.
3. **Track the outcome via webhooks** — listen for `TransactionSettled` (settled) or `TransactionRejected` (rejected), and `InboundHeldTransaction` / `OuboundHeldTransaction` if screened. Reply `200` with the signed `Nonce` within 5 seconds.
4. **Return a payment if needed** — `POST /v3/payments/fps/return` (`PostReturn`) to return an inbound payment.

## Rules
- Payment initiation is asynchronous: `202` means accepted, not settled — settlement is confirmed only by webhook.
- Keep webhook handlers idempotent (at-least-once delivery, retried every 15 min for 24h).
