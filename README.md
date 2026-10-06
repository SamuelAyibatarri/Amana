# Amana

A custodial Solana wallet that lives inside WhatsApp. Buy crypto with naira,
send to any phone number or Solana address, and get a verifiable receipt for
every payment — all in plain chat, no seed phrases, no gas math.

Built for the Crypto World's Fair hackathon
([Superteam Nigeria track](https://superteam.fun/earn/listing/colosseum-crypto-worlds-fair-hackathon-superteam-nigeria-track)).

## Repos

| Repo | What |
|---|---|
| [`amana-backend-azure`](https://github.com/SamuelAyibatarri/amana-backend-azure) | Bun + Hono bot backend (Baileys WhatsApp socket, Solana Devnet, AI intent parsing) |
| [`amana-frontend`](https://github.com/SamuelAyibatarri/amana-frontend) | Next.js web app (KYC, dashboard, receipts, Paystack on-ramp) on Cloudflare |

This repo is the index — the two projects above are included as submodules.
Clone everything at once:

```bash
git clone --recurse-submodules https://github.com/SamuelAyibatarri/Amana.git
```

Already cloned without submodules? Fill them in:

```bash
git submodule update --init --recursive
```

## How it works (30 seconds)

1. Say hi to the bot on WhatsApp — it onboards you and hands you a sign-in link.
2. Verify identity (BVN + NIN) on the web app.
3. Transact in chat: *"buy 2000 naira of sol"*, *"send 0.5 SOL to 0803..."*.
   Every payment ends with a receipt image you can verify.

Under the hood: one treasury wallet signs and pays everything (gasless for
users), an internal ledger settles phone-to-phone transfers instantly, and
liability-matched mirror pools on Solana Devnet prove every unit of user
money is backed 1-to-1 (`/health/mirror`).

## Disclosure

Hackathon build: verification is mocked, funds live on Solana Devnet,
payments run through Paystack test mode — **no real money moves.**

## Demo video

Coming soon (link will be added before submission).
