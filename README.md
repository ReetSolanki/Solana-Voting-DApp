# Voken — Solana Voting dApp

A decentralized voting application built on Solana where users buy tokens with SOL to vote on proposals.

---

## Features

- **Token-based Voting** — Purchase voting tokens with SOL and cast votes on active proposals
- **Proposal Management** — Create proposals with deadlines and token stakes
- **Voter Registration** — Register on-chain to participate in governance
- **Winner Selection** — Automatically determine winners after voting deadline
- **Treasury System** — Admin-controlled treasury managing token mint and funds

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Smart Contract | Rust + Anchor Framework |
| Frontend | React + Vite |
| Blockchain | Solana (Devnet) |
| Wallet | Phantom |

---

## Project Structure

vote/
├── vote_app/                  # Anchor program (Solana smart contract)
│   └── programs/vote_app/src/
│       ├── lib.rs             # Main program logic & instruction handlers
│       ├── contexts.rs        # Account validation contexts
│       ├── state.rs           # On-chain account structures
│       ├── errors.rs          # Custom program errors
│       └── events.rs          # Program events
│
└── client/                    # React frontend
└── src/
├── components/        # UI components
├── idl/               # Program IDL (auto-generated)
└── constants/         # App constants & config

---

## Getting Started

### Prerequisites

- [Node.js 18+](https://nodejs.org/)
- [Rust & Cargo](https://www.rust-lang.org/tools/install)
- [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
- [Anchor CLI](https://www.anchor-lang.com/docs/installation)
- [Phantom Wallet](https://phantom.app/)

### Run the Frontend
```bash
cd client
npm install
npm run dev
```

### Build & Deploy the Program
```bash
cd vote_app
anchor build
anchor deploy
```

> Make sure your Solana CLI is pointed at devnet: `solana config set --url devnet`

---

## Program Instructions

| Instruction | Description |
|-------------|-------------|
| `initialize_treasury` | Set up treasury with token mint and pricing |
| `buy_tokens` | Purchase voting tokens with SOL |
| `register_voter` | Register a voter account on-chain |
| `register_proposal` | Create a new proposal with a token stake |
| `proposal_to_vote` | Cast a vote on an active proposal |
| `pick_winner` | Declare the winner after the deadline passes |
| `close_proposal` | Close a proposal and recover rent |
| `close_voter` | Close voter account and recover rent |
| `withdraw_sol` | Admin withdraws SOL from the treasury |

---

## License

MIT
