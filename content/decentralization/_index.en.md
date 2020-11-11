---
date: 2020-11-11T00:0:00+00:00
title: Decentralization
weight: 8
---

The standard Serum DEX is decentralized. What does this mean?

- It’s open-source

  - In general, Serum code is in https://github.com/project-serum/awesome-serum
  - In this case:
    - On-chain code: https://github.com/project-serum/serum-dex
    - GUI code: https://github.com/project-serum/serum-dex-ui
    - Code for interfacing with the DEX: https://github.com/project-serum/serum-js

- Anyone can create SPL tokens

  - On-chain program is https://explorer.solana.com/address/TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA
  - A GUI to do it: https://spl-token-ui.netlify.app/#/
    - Source code: https://github.com/paul-schaaf/spl-token-ui

- Anyone can add markets to the DEX; it’s not permissioned

  - And you can list a market for any two SPL tokens
  - https://serum-academy.com/en/add-market/
  - https://dex.projectserum.com/#/list-new-market and https://bonfida.com/dex/#/list-new-market for GUIs

- Anyone can host a GUI on the DEX; that’s also not permissioned

  - https://serum-academy.com/en/hosting-gui/

- Anyone can trade on any of the DEX markets; they’re not permissioned

  - https://github.com/project-serum/serum-dex
  - https://github.com/project-serum/serum-js has some interfacing code to make it easier to do
  - Anyone can use any DEX on this list: https://serum-academy.com/en/dex-list/

- Roughly 20 independent parties are hosting DEX GUIs

  - https://serum-academy.com/en/dex-list/

- The DEX is fully on-chain: the orderbook, matching engine, etc. are all on-chain, and don’t rely on some separate, centralized server to match trades.

- The Serum DEX is fully non-custodial; the tokens only travel between your personal wallet and on-chain programs which behave deterministically
