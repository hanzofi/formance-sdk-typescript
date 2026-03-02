# @hanzofi/sdk

TypeScript SDK for the Hanzo Fi Stack. Client library for Ledger, Payments, Wallets, Reconciliation, and Flows APIs.

## Installation

```bash
npm install @hanzofi/sdk
# or
pnpm add @hanzofi/sdk
```

## Usage

```typescript
import { SDK } from "@hanzofi/sdk";

const sdk = new SDK({
  serverURL: "http://localhost:8080",
  security: { authorization: "Bearer <token>" },
});

// Create a ledger transaction
const result = await sdk.ledger.createTransaction({
  ledger: "default",
  postTransaction: {
    postings: [{
      source: "world",
      destination: "users:001",
      amount: BigInt(10000),
      asset: "USD/2",
    }],
  },
});

// List payments
const payments = await sdk.payments.listPayments({});

// Get wallet balance
const balance = await sdk.wallets.getBalance({
  walletId: "wallet-001",
});
```

## Available Services

- `sdk.ledger` — Double-entry ledger operations
- `sdk.payments` — Payment provider operations
- `sdk.wallets` — Virtual wallet management
- `sdk.reconciliation` — Transaction matching
- `sdk.orchestration` — Workflow management
- `sdk.webhooks` — Webhook configuration
- `sdk.auth` — Authentication

## License

MIT — see [LICENSE](LICENSE)

