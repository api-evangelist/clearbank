---
name: Initiate a CHAPS RTGS payment
description: Send a high-value CHAPS (RTGS) institution or customer payment on ClearBank and handle returns.
api: openapi/clearbank-chaps-v6.json
operations: [ExternalCreateInstitutionPayment-v6, ExternalCreateCustomerPayment-v6, ExternalReturnPayment-v6]
---

# Initiate a CHAPS RTGS payment

ClearBank is a direct CHAPS participant. Use v6 of the CHAPS API.

## Auth (every request)
- `Authorization: Bearer <API token>`, an RSA `DigitalSignature` over the body, and a unique `X-Request-Id`.

## Steps
1. **Choose the payment type**
   - Bank's own payment: `POST /payments/chaps/v6/institution-payments` (`ExternalCreateInstitutionPayment-v6`).
   - On behalf of a customer: `POST /payments/chaps/v6/customer-payments` (`ExternalCreateCustomerPayment-v6`).
   - Both return `202 Accepted`. `400` = validation / bad `X-Request-Id`; `404` = account not found.
2. **Track settlement via webhooks** — `TransactionSettled` on success, `TransactionRejected` on failure, held events if screened. Reply `200` echoing the signed `Nonce` within 5 seconds.
3. **Return an inbound CHAPS payment** — `POST /payments/chaps/v6/return-payments` (`ExternalReturnPayment-v6`).

## Rules
- CHAPS is high-value RTGS — validate the creditor with Confirmation of Payee first where applicable.
- `202` is acceptance only; rely on the webhook for the settlement outcome.
- Errors are RFC 7807 `ProblemDetails`.
