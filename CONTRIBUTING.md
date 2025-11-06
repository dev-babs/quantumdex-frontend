# Frontend Contribution Guide (issues)

This file lists tasks that should be created as GitHub issues (label: `frontend`). Contributors can pick one, create a branch `issue/<id>-short-description`, implement, then open a PR referencing the issue.

- Wallet Integration — Reown AppKit + Wagmi

  - Short: Add wallet connection UI and provider wiring.
  - Description: Implement connection using Reown AppKit and Wagmi, exposing a `Navbar` component that shows connect/disconnect, address, and network.
  - Acceptance: Users can connect via MetaMask and WalletConnect; an ethers signer is available from the provider.

- Ethers/Wagmi Adapter & Provider

  - Short: Provider and adapter utilities
  - Description: Create `src/config/wagmi.ts` and `src/config/adapter.ts` to expose providers and signers.
  - Acceptance: Components can retrieve provider and signer via hooks.

- Port `lib/amm.ts` to ethers (contract bindings)

  - Short: Contract helpers
  - Description: Replace Clarity helpers with ethers contract wrappers for AMM contract functions and event parsing.
  - Acceptance: `getAllPools`, `createPool`, `addLiquidity`, `removeLiquidity`, `swap`, `getUserLiquidity` exist and return typed results.

- Swap Component

  - Short: Swap UI
  - Description: Port `src/components/swap.tsx` to use new helpers and signer for swap transactions.
  - Acceptance: User can estimate outputs and send a swap transaction from the UI.

- Pools List & Pool Details

  - Short: Pools listing and detail pages
  - Description: Build UI to list pools (from events or contract state) and show pool details with balances.
  - Acceptance: Pools display correctly and pool pages show balances/liquidity.

- Add / Remove Liquidity Components

  - Short: Liquidity management UI
  - Description: Implement add/remove liquidity flows with ratio computations and validations.
  - Acceptance: Transactions created with expected arguments; UI shows results.

- Create Pool Component

  - Short: New pool creation
  - Description: Enable users to create pools (token pair + fee) ensuring deterministic token ordering.
  - Acceptance: Contract emits pool-created event and pool becomes visible in listing.

- Styling & Accessibility

  - Short: UI polish
  - Description: Use Tailwind to ensure responsive and accessible components.
  - Acceptance: Accessible labels and focus states; mobile layout verified.

- Tests: Unit & Integration
  - Short: Frontend tests
  - Description: Add unit tests for utilities and integration tests for flows (connect, swap, add liquidity).
  - Acceptance: CI runs tests and reports pass/fail.

PR checklist (frontend):

- [ ] Linted and type-checked
- [ ] Tests added or updated (if applicable)
- [ ] Reviewed and approved by at least one maintainer
- [ ] Linked to a GitHub issue
