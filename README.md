# ClearBank (clearbank)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

ClearBank is a UK clearing and Banking-as-a-Service bank, founded in 2015 by Nick Ogden (founder of WorldPay) and Charles McManus and granted a banking licence in December 2016 as the first new UK clearing bank in more than 250 years. Authorised by the Prudential Regulation Authority and regulated by the FCA and PRA (FRN 754568), it is a direct participant in the UK payment schemes (Faster Payments, CHAPS, Bacs) and delivers Agency Banking, Embedded Banking, and Transaction Banking to banks, fintechs, and corporates through a single, cloud-native (Microsoft Azure) proprietary JSON REST API. Unlike the CMA9 retail banks, ClearBank is not a mandated Open Banking ASPSP and does not publish OBIE Open Data or OBIE Read/Write APIs.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/clearbank/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/clearbank/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Banking as a Service
- Embedded Banking
- Payments
- Clearing
- Faster Payments
- CHAPS
- Multi-Currency
- Foreign Exchange
- Open Banking
- United Kingdom
- Fintech

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## API Access

The ClearBank Financial Institutions API is available to FCA-regulated businesses, banks, corporates, and fintechs that have been onboarded with ClearBank.

- **Production base URL:** `https://institution-api.clearbank.co.uk`
- **Simulation base URL:** `https://institution-api-sim.clearbank.co.uk`
- **Authentication:** API token in the `Authorization` header, plus an RSA (SHA-256, PKCS#1 v1.5) `DigitalSignature` header over the request body and a unique `X-Request-Id` header per request.

## APIs

### ClearBank GBP Accounts API

Open and manage sterling accounts, retrieve account details, balances, transactions, Bacs data, and reporting.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-sterling-v4.json)

### ClearBank Faster Payments API

Initiate and manage UK Faster Payments (FPS) and internal transfers.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-fps-initiate-payment-v3.json)

### ClearBank CHAPS API

Initiate and manage high-value CHAPS RTGS payments, returns, and bank-to-bank settlement.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-chaps-v6.json)

### ClearBank Multi-Currency Accounts API

Create and manage multi-currency (MCCY) accounts and retrieve balances, transactions, and statements.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-mccy-accounts-v2.json)

### ClearBank Multi-Currency Payments API

Orchestrate outbound and inbound multi-currency payments across supported currencies and rails.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-mccy-payments-v1.json)

### ClearBank FX API

Foreign-exchange trading orchestration supporting spot and request-for-quote (RFQ) currency conversion.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-fx-orchestrator-rfq.json)

### ClearBank SEPA Credit Transfer API

Send and receive SEPA Credit Transfer (SCT) euro payments across the Single Euro Payments Area.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-sepa-ct-v1.json)

### ClearBank Confirmation of Payee API

Outbound Confirmation of Payee (CoP) name-checking to reduce misdirected payments and APP fraud.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-cop-outbound-v1.json)

### ClearBank Customer Due Diligence (KYC) API

Know Your Customer / Customer Due Diligence checks for onboarding and verifying customers.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-know-your-customer-v1.json)

### ClearBank Cross-Border Sterling Payments API

Cross-border sterling payment initiation and management for international transfers.

- **Human URL:** [https://clearbank.github.io/uk/docs/api/](https://clearbank.github.io/uk/docs/api/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-cross-border-v4.json)

### ClearBank Retail Embedded Banking Customers API

Embedded Banking APIs to create and manage retail customers, hub and payment accounts, savings, and ISAs.

- **Human URL:** [https://clearbank.github.io/uk/docs/embedded-banking/retail-customers/](https://clearbank.github.io/uk/docs/embedded-banking/retail-customers/)
- **Base URL:** `https://institution-api.clearbank.co.uk`
- [OpenAPI](openapi/clearbank-customers_v2_retail.json)

## Common Properties

- [Website](https://www.clear.bank/)
- [Developer Portal](https://clearbank.github.io/)
- [Documentation](https://clearbank.github.io/uk/docs/api/)
- [Getting Started](https://clearbank.github.io/uk/docs/api/getting-started/)
- [GitHub Organization](https://github.com/clearbank)
- [LinkedIn](https://www.linkedin.com/company/clearbank)
- [Blog / Newsroom](https://clear.bank/newsroom)
- [Security](https://clear.bank/security)
- [Terms of Service](https://clear.bank/legal/terms-and-conditions)
- [Privacy Policy](https://clear.bank/data-protection-and-privacy)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
