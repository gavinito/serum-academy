---
date: 2020-08-30T00:0:00+00:00
title: Project Ideas for Serum
weight: 2
---

## Project Ideas

If you want to know how to get involved on these projects see our dedicated page: [Getting involved](/en/getting-involved)

Developer resources can be found on: [https://projectserum.com/developer-resources](https://projectserum.com/developer-resources)

Feel free to reach out to us if you are interested in any of these projects:

- EcoSerum website: [https://www.ecoserum.dev/](https://www.ecoserum.dev/)
- EcoSerum Telegram: [@ecoSerum](https://t.me/ecoSerum)
- Email: [contact@projectserum.com](mailto:contact@projectserum.com)
- Twitter: [@ProjectSerum](https://twitter.com/ProjectSerum)
- Discord: [Project Serum](https://discord.com/invite/MxZFT4v)

See the list of awarded grants on Project Serum dedicated section: [https://projectserum.com/grants](https://projectserum.com/grants)

### AMM Bot

Building an open source system that people can use to achieve AMM-like behavior on Serum’s orderbooks.

If you build it to the below specs, it will receive a predetermined bounty instead of the variable one.

**Bounty**: 75k locked SRM

**Specs**:

- Can support 2-token AMM or more

- Must trade via the orderbooks by:

  - (a) Putting out a set of offers with a depth curve that matches the AMM curve
  - (b) Doing the same with bids
  - (c) Whenever an offer gets filled, replace it with a bid at the same price/size (post-only), and vice versa when a bid gets filled

- Parameters must be reasonable

- Must be functional

- Must have pool tokens

- Must be open source

- Must be able to launch new AMMs with arbitrary SPL tokens

- Orderbooks:

_Note: A draft of an implementation of AMMs on Solana can be found on the [GitHub account](https://github.com/solana-labs/solana-program-library/tree/master/token-swap) of Solana Labs._

### Dumplings

A yield farming token that is integrated into an AMM system on Serum.

Here is an idea of what it could look like:

- Build a "pool" which starts at 100 SRM + 100 SOL per pool token. It's just an ETF — you can't actually trade against the pool.

- The pool automatically does the on-chain AMM-style market making on the Serum SRM/SOL market. Basically this means; a liquidity providing strategy such that, if SRM/SOL goes from price A → B → A, the pool’s valuation will at worst be unchanged. The pool will be fully on-chain and its behavior will be well defined from creation.

- You can 'create' into the pool by delivering the basket. So at the beginning if you send in 200 SRM + 200 SOL you get 2 SPT (Serum Pool Tokens). If after an hour of trading the pool was 150 SRM + 80 SOL then to create 2 SPT you'd deposit 300 SRM + 160 SOL.

- You can redeem your SPTs for the fractional share of the pool.

- The pool gets the proceeds of its trading, including maker rebates

- Each day, 10,000 Dumplings are added to the pool for the first 100 days; then no more Dumplings are created. When a Dumpling contract is first created, 100,000 Dumplings (DUM) are airdropped on all SRM holders to seed liquidity for joining the pool.

This means that:

- If you redeem your SPTs after 5 days and you were half the pool, you'd get back your SRM/SOL, and also 25,000 Dumplings. You can trade those on the DUM/USDC market or whatever.

- If after 5 days you want to _join_ the SRM/SOL MM pool for, say, 100 SRM + 100 SOL, you'd have to send in: 100 SRM, 100 SOL, and some DUM (maybe 15,000, depending on how large the pool had been/how many DUM are in 1 SPT).

This means that entering the MM pool is gated by buying/owning Dumplings, and you get Dumplings each day for providing liquidity.

### Borrow/Lending

If you build it to the below specs, it will receive a predetermined bounty instead of the variable one.

**Bounty**: maximum (100k locked SRM)

**Specs**:

- Can be isolated between pairs, or cross between all pairs

- Must at least include the following SPL tokens: USDT, USDC, BTC, ETH, SOL (or wrapped SOL), SRM, FTT, SUSHI, MSRM, YFI, LINK.

- Must be seamlessly composable onto trades

- Parameters must be reasonable

- Must be functional

- Fees must be either:

- Predetermined at the creation of a pool
- Set via a vote of SRM nodes
- Set via a vote of the protocol’s token

- 100% of fees paid to BORROW/LENDING token

  - Consistent with the general [EcoSerum token plan](/en/serum-project-ideas/serum-ecosystem)

- Must be open source

- Must be able to launch new books with arbitrary SPL tokens

### Sushi Swap

_Notes: This is submitted on behalf of [EcoSerum](https://www.ecoserum.dev), a Serum node. Serum Academy is involved in the development of Serum but has not been involved in the development of Sushi in any way._

#### Proposal

- The Sushi community builds out support for Sushiswap on Solana
- Sushi rewards are paid to both Ethereum and Solana/Serum based Sushiswap
  - Proportional to the TLV in each
  - Or alternately fixed to each pool
  - Open to other suggestions as well--what’s fair?
- The Sushi community composes this with the Serum orderbooks
  - Each Sushi pool has a curve, currently constant-product
  - The pool sends bids/offers into the associated Serum orderbook to simulate that curve
  - This allows the Sushi AMM to share liquidity and volume with the orderbook
  - There are maker rebates on Serum orderbooks that the AMMs would capture; they can also add on their own fees
- [FTX](https://ftx.com) has a bridge from ERC20 <> SPL (Solana token) Sushi; in the next week, [Sollet.io](https://sollet.io) will as well
- Sushi will also be able to compose with a borrow/lending protocol on Serum to allow the pools to trade on margin, though that’s not necessary for V1
- To clarify: Sushi would not be moving off of Etherum in any way; this would be an addition, not a replacement.

#### Rewards

- [EcoSerum](https://www.ecoserum.dev), a Serum node that helps build out the community, will give the following rewards:
- 50k SRM for 1+2
- 1 locked MegaSerum for 1-5
  - One MegaSerum is 1 million Serum put together
  - This will allow the Sushi community to participate in Serum, run a node, receive yield, benefit from a buy/burn, and receive discounts
  - This will be locked (not sellable or transferable) for 1-7 years: fully locked until Aug 1 2021, and then unlocking linearly over the 6 years after that
- These rewards are for the Sushi community, controlled by governance, to do what they want with
- In addition, 20k SRM for 1+2 and another 10k for 1-5 to the team who builds it

#### Timeline

The target would be for pieces of this to roll out within a month, and completion before the end of 2020. The assumption is that work would not start in earnest until after the Sushiswap migration is complete.

### Pools

Bounty: **25k locked SRM**

Build token pools with the following features:

- Create/redeem pools based on their underlying assets
- Pools can be program-controlled, address-controlled, or keyless
- Charge fees for creating/redeeming
- Create a token, fees -> buy/burn of token; following standard EcoSerum guildlines for the token

### Cross-Chain Bridges

It would be awesome to have fully on-chain bridges between Solana and as many other chains as possible. See prospective specs for one here, but there are many other versions!

### Swipe Integration

Build a project with the following properties:

- Swipe generates a new Solana wallet address A, gets the private key
- Swipe creates another Solana wallet address A2 controlled by the first one and passes that secret key on to the user
- When an incoming payment request comes for \$D, Swipe: (a) freezes withdrawals from A2 and everything it owns; (b) adds up the value of assets in A2 and everything it owns; and (c) determines if it's > D or not. If so it sells assets into USDC until it hits D on the Serum orderbooks, withdraws that, and then approves the request; otherwise it denies it.
- **Optional:** Tack on 0.25% of fees for the transactions and use those to buy/burn an SPL token T; T has 1b total tokens and airdrops them over 7 years onto SRM stakers, possibly + SPL SXP holders
- Reward: 20% of T tokens, 1-7 year lockup

### Cross-Chain Lending

Assets can be pre-funded across the bridge and allow users to avoid waiting for cross-chain synchronization for a fee. For example, a user could deposit X eth into the bridge as collateral, and be able to withdraw any pre-funded assets up to some limit.

### Serum Oracle

An on-chain oracle that takes prices from Serum markets, does sophisticated risk and sanity checks on them, and creates a clean price feed that other projects working on Serum can use. Furthermore, once there are on-chain cross-chain bridges, those can be combined with this to create a fully on-chain cross-chain pricing oracle.

### Serum RFQ

Generate a tradable RFQ from the Serum order book. The generated quote can be valid for a limited time and backed by an insurance pool. It would have a size attached, and potentially be larger and wider than would be typical for orderbook trading.

### Decentralized Wrappers

An on-chain method of wrapping an ERC20 token into an SPL token and vice versa.

### Synthetic Assets

Building out support for tokenized synthetic assets on Serum.

### Volatility Products

Building out markets or tokenized products representing volatility or other nonlinear functions of markets.

### Zero Knowledge Liquidation Engine

PoC for ZK liquiditations, where it’s zk to the network, but not zk to the defi platform operators. The engine should be able to use the on chain order book price or funding rate as a witness, and generate a proof that states the contract is now ‘in the money’ or ‘out of the money’ and take an action from there.

### Native Metamask Integration

See this introduction to Web3 Plugins for more details

### Messaging Application

Bounty: **Bounty of 25k locked SRM**

Build an instant messaging app on Solana with the following:

- The app would pass encrypted messages over the network
- Build a GUI for people to chat with each other

### Mobile App

If you build it to the below specs, it will receive a predetermined bounty instead of the variable one.

**Bounty**: 50k locked SRM

**Specs**:

- Generally well built

- Built in self-custody wallet that supports SPL tokens and SOL

- Supports the core functions of [https://serum-academy.com/en/dex-list/](/en/dex-list/)

- Released on apple and android app stores

- Note you will also get [GUI rewards](/en/dex-list)

### Badges

Badges to represent participation in various aspects of Serum; e.g. liquidity providing, node operating.

### SPL Name Service

Create a table where the mint of a token can submit a name for their token. Also create a table where a token controls governance of the naming. If you create this, EcoSerum will support the token's adoption; you get 20% of them.

### GUI & Other Ideas

Below is a list of GUI & other features that could be developed:

- Button on [Sollet.io](https://sollet.io) to mint your own SPL token
- Graphs on the DEX GUI
- Button to create a Serum market
- Market orders on GUI
- Ledger support for [Sollet.io](https://sollet.io)
- Volume and other metric trackers for Serum
- A tool to validate GUIs against the source code
- Build support for on-chain triggered orders (stop losses, take profits) into Serum.
- Add Ledger support on Serum DEX UI

See Project Serum [GitHub account](https://github.com/project-serum/) for the source of [Sollet.io](https://sollet.io) and the [DEX GUI](/en/dex-list)
