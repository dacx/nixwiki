---
description: Commonly asked about network and coin specifications
---

# Network and Coin Specs

## NIX \(Native UTXO\)

### Network

|  |  |
| :--- | :--- |
| Codebase | BTC 0.17 |
| Mainnet Port | 6214 |
| Testnet Port | 16214 |
| Consensus | [Proof of Stake/Custom LPoS](consensus.md) |
| Block Time Target | 2 minutes |
| Difficulty Adjustment | Every block, 2 block moving average |
| Max. Block Size | 1MB |
| Est. TPS | 80 |

### Coin

|  |  |
| :--- | :--- |
| Current Supply | ~48,205,000 \(DEC 2020\) |
| Maximum Supply | 102,210,160 \(After 40 years\) |
| Staking Reward | ~2.7 per block |
| Development Fund | 1.28 per block |
| Ghostnode Reward \* | 8.448 per block |
| Ghostnode Ghost Vault Fee \*\* \(1-way Ghosting\) | .25% |
| Ghostnode Vault to Vault TX Fee \*\* \(2-way Ghosting\) | .1 Ghosted NIX |

\*- Node rewards are paid to 1 Ghostnode at a time, repeatedly cycling through the list of active nodes. Currently, this means a Ghostnode owner can expect 2 rewards per day \(16.896 NIX\).  
\*\*- Vault fees are pooled and split among all active Ghostnodes on a daily basis.

### Inflation/Halving Schedule

Staking rewards are not subject to scheduled reductions, but instead, slowly increase over time until the maximum supply is reached at a rate of 1.5% per year.

Ghostnode and Development rewards are halved every 4 years, with the first one expected to happen in June/July 2022.

Overall inflation is approximately 3 million NIX per year.

### Live Network Stats

Live data and network stats can be [found here](https://data.nixplatform.io/) on the NIX website.

## NBT \(ERC20 Governance Token\)

Ethereum Token Contract: 0x2e2364966267b5d7d2ce6cd9a9b5bd19d9c7c6a9  
UNI-v2 LP address: 0x06e4c11eaac88ae9253f9e86b60c8b4e7d4b281c  
Circulating Supply: 32,613  
Total Supply: 44,613  
Burnt Tokens: 15,387  
Maximum Supply: 60,000  
Inflation Rate: None

