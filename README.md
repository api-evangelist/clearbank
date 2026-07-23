# ClearBank (clearbank)

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
