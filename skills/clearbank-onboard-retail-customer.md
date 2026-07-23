---
name: Onboard a retail embedded-banking customer
description: Create and verify a retail customer (KYC) with identity documents on ClearBank Embedded Banking.
api: openapi/clearbank-customers_v2_retail.json
operations: [V2RetailPost, V2CustomerGet, V2CustomerIdentityDocumentPut, V2CustomerTaxResidencyPut, V2RelatedPartyPost]
---

# Onboard a retail embedded-banking customer

## Auth (every request)
- `Authorization: Bearer <API token>`, an RSA `DigitalSignature` over the body, and a unique `X-Request-Id`.

## Steps
1. **Create the retail customer** — `POST /customers/v2/retail` (`V2RetailPost`) with the customer's personal details.
   - `201 Created` on success; `422` = validation failure; `409` = duplicate.
2. **Attach identity documents** — `PUT /customers/v2/customers/{customerId}/identity-documents/{idCountryOfIssue}-{idType}` (`V2CustomerIdentityDocumentPut`).
3. **Record tax residency** — `PUT /customers/v2/customers/{customerId}/tax-residencies/{countryOfTaxResidence}` (`V2CustomerTaxResidencyPut`).
4. **Add related parties if needed** — `POST /customers/v2/customers/{customerId}/related-parties` (`V2RelatedPartyPost`).
5. **Poll / read status** — `GET /customers/v2/customers/{customerId}` (`V2CustomerGet`).
6. **Await the KYC outcome via webhooks** — `RetailCustomer.ApplicationSuccessful`, `RetailCustomer.ApplicationDeclined`, or `RetailCustomer.AdditionalInfoRequired`. Reply `200` with the signed `Nonce` within 5 seconds.

## Rules
- KYC/CDD outcomes are asynchronous — do not assume success from the `201`; wait for the `RetailCustomer.*` webhook.
- Errors follow RFC 7807 `ProblemDetails`; validate before submitting to avoid `422`.
