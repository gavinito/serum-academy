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
- Discord: [Project Serum](https://discord.gg/8UwqSaf)

See the list of awarded grants on Project Serum dedicated section: [https://projectserum.com/grants](https://projectserum.com/grants).

{{% notice warning %}}
There is no guarantee that you will receive a grant. Please contact [EcoSerum](https://t.me/ecoSerum) to know whether the project you are interested in is eligible for a grant.
{{% /notice %}}
{{% notice warning %}}
Grants might or might not be available after the first implementation for future ones
{{% /notice %}}

### AMM Bots using Pools

Building an open source system that people can use to achieve AMM-like behavior on Serum. There are lots of variants and customizability but here are some ideas:

- AMMs that trade on Serum's markets
- AMMs with more than two components
- AMMs with easy to customize curves

If you build it to the below specs, it will receive a predetermined bounty instead of the variable one.

**Bounty**: 75k locked SRM

**Specs**:

- Parameters must be reasonable

- Must be functional

- Must have pool tokens

- Must be open source

- Must be able to launch new AMMs with arbitrary SPL tokens

_Note: A draft of an implementation of AMMs on Solana can be found on the [GitHub account](https://github.com/solana-labs/solana-program-library/tree/master/token-swap) of Solana Labs._

#### Sushi Swap

_Notes: This is submitted on behalf of [EcoSerum](https://www.ecoserum.dev), a Serum node. Serum Academy is involved in the development of Serum but has not been involved in the development of Sushi in any way._

##### Proposal

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

##### Rewards

- [EcoSerum](https://www.ecoserum.dev), a Serum node that helps build out the community, will give the following rewards:
- 50k SRM for 1+2
- 1 locked MegaSerum for 1-5
  - One MegaSerum is 1 million Serum put together
  - This will allow the Sushi community to participate in Serum, run a node, receive yield, benefit from a buy/burn, and receive discounts
  - This will be locked (not sellable or transferable) for 1-7 years: fully locked until Aug 1 2021, and then unlocking linearly over the 6 years after that
- These rewards are for the Sushi community, controlled by governance, to do what they want with
- In addition, 20k SRM for 1+2 and another 10k for 1-5 to the team who builds it

### Messaging Application

Bounty: **Bounty of 25k locked SRM**

Build an instant messaging app on Solana with the following:

- The app would pass encrypted messages over the network
- The app would be fully on-chain
- Build a GUI for people to chat with each other
- The app could be directly integrated to Serum DEX GUI

### Yield Farming

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

### Serum Oracle

An on-chain oracle that takes prices from Serum markets, does sophisticated risk and sanity checks on them, and creates a clean price feed that other projects working on Serum can use. Furthermore, once there are on-chain cross-chain bridges, those can be combined with this to create a fully on-chain cross-chain pricing oracle.

**Specs**:

- Takes in arbitrary signals
  - Can take from multiple sources
  - Combines in a reasonable way
- Has reasonable error handling and outlier handling
- Writes on-chain
- Some way to charge people for querying it on-chain
- A built-in way to use Serum orderbooks as an oracle

### Token Minter Panel

A token minter panel with the following specs:

- Mint SPL tokens
- Specify an address and market
  - Funds there go to buy/burn that token on that market
  - If the funds are that token they’re natively burnt
- Options to be able to keep minting, or probably throw away the key to mint more

### SPL Name Service

Create a table where the mint of a token can submit a name for their token. Also create a table where a token controls governance of the naming. If you create this, EcoSerum will support the token's adoption; you get 20% of them.

### Cross-Chain Bridges

It would be awesome to have fully on-chain bridges between Solana and as many other chains as possible. Cross-chain bridges would be decentralized. See prospective specs for one [on Sollet.io](https://github.com/project-serum/spl-token-wallet), but there are many other versions!

### Exchanges

If you are an exchange and want to add Solana, SRM and SPL support please reach out to us.

### Native Metamask Integration

Native MetaMask integration for Solana, SRM and SPL tokens. See [this introduction](https://medium.com/metamask/introducing-the-next-evolution-of-the-web3-wallet-4abdf801a4ee) to Web3 Plugins for more details

### Security Audits

Security audits of the following repositories:

- https://github.com/serum-foundation/spl-token-wallet
- https://github.com/project-serum/sol-wallet-adapter
- https://github.com/project-serum/serum-dex-ui
- https://github.com/project-serum/serum-dex

### App Store

Create a Serum app store that would allow people to navigate to all common Serum apps from a single page. This way everyone would be exposed to everything from: Cryptocurrencies.ai, Bonfida, Coin98,various AMM apps, wallets etc...

**Bounty**: 40k

### GUI Improvements

Below is a list of GUI improvements that could be developed:

- Button on [Sollet.io](https://sollet.io) to mint your own SPL token
- Ledger support for [Sollet.io](https://sollet.io)
- Volume and other metric trackers for Serum
- A tool to validate GUIs against the source code
- Build support for on-chain triggered orders (stop losses, take profits) into Serum.
- Add Ledger support on Serum DEX UI
- Auto-dropping a bit of SOL to get people started on Solana wallets
- Wallet Address management: a system that would look like this
  - A wants to send token X to B
  - B says "my SOL address is S"
  - A creates an account for X owned by S and then sends X to that account
  - B then searches for all locations where they own X, finds that account, and adds it to the GUI

See Project Serum [GitHub account](https://github.com/project-serum/) for the source of [Sollet.io](https://sollet.io) and the [DEX GUI](/en/dex-list)

### Other projects the Serum community is excited about

- Other social networking applications
- General yield farming
- Hosting Solana validators and RPC servers for Serum usage
- Serum app store, or other way to easily collect popular dapps on Solana
  https://twitter.com/StaniKulechov/status/1322232473930137603
- Add Serum DEX markets that use aTokens, cTokens, yTokens, etc.; make the UI intuitive; so that it’s like other Serum DEXes except open orders are interest bearing
- Make the prices look like normal BTC/USDC prices etc.
- Easy ways to go from e.g. aUSDT_SOL → aUSDT_ETH → USDT_ETH and aUSDT_SOL → USDT_SOL
- Great info, GUI display, querying, external API, on-chain API, etc. of Serum data:
  - Dex.projectserum.com
  - Swap.projectserum.com
  - SPL token transfers
- Make explorer.solana.com great again
  - When you go to an address and see a history of transactions, there should be a column for (approximate) time, not just block number
  - If you go to a token mint address, token address, or transaction, you should see a (history of) all SOL and SPL token transfers associated with it
  - Transaction parsing for serum dex and swap.projectserum.com
  - “October 28, 2020 at 24:19:50 China Standard Time” should be 00:19:50 (e.g. https://explorer.solana.com/tx/sYdyGKLWqSEjZkSWMCf3o28giXWyx569FAHbeVc4XFuqgvJ52XQ6TvJMnwdGmM76aS2pkePcymqCPBPvmAZUKYe)
  - Building an API into the explorer so you can easily query things like “total SRM sent to address X from time t1 to time t2” and things like that
- Swerve: https://twitter.com/SwerveFinance/status/1320864824042008578
