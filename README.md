# OnChainAnalysisGuide

Reading the blockchain: wallets, transactions, holders, and flows. On-chain analysis means studying the public record of a blockchain itself — transactions, addresses, and balances — instead of relying only on price charts or social media.

> This guide is educational only, not financial advice. On-chain data is public, but interpreting it is easy to get wrong, and it never proves a future price move.

## 1. Why on-chain data is different

A blockchain is a public ledger. Anyone can inspect:

- Every transaction: sender, receiver, amount, fee, and time.
- Every address's balance and history.
- Every token's total supply, holders, and transfers.
- Every smart contract's code (if verified) and interactions.

This is radically more transparent than traditional finance, where most flows are private. But transparency is not the same as clarity: addresses are pseudonymous, one person can control many addresses, and one address (such as an exchange's) can represent millions of people.

## 2. Tools of the trade

### Block explorers
A block explorer (such as Etherscan, BscScan, or Solscan) lets you look up any transaction, address, token, or contract by its hash or address.

Use it to verify, not to guess:

- Did a transaction actually happen? Search its hash.
- Does a token contract match the project's official address?
- Who are the largest holders, and how concentrated is supply?

### Analytics platforms
Platforms such as Glassnode, CryptoQuant, Nansen, and Dune aggregate on-chain data into charts and dashboards: exchange flows, holder behaviour, network activity, and more.

- Free tiers cover the basics; advanced metrics are often paid.
- Dashboards built by the community (Dune) vary wildly in quality — check the author's method before trusting a chart.

### Portfolio trackers
Tools that connect to your addresses (read-only, never by sharing a seed phrase) and show your balances across chains. Useful for record-keeping, but they are not a substitute for checking the explorer yourself for important transactions.

**Security warning:** a legitimate tracker only needs your public address. Any tool that asks for your seed phrase or private key is a scam.

## 3. Reading a transaction

A typical transaction record shows:

- **Hash:** the transaction's unique ID. Share this, not screenshots, when proving a transaction happened.
- **Status:** success or fail. A failed transaction can still cost gas.
- **From / To:** sender and receiver addresses. "To" may be a wallet, or a contract (for a swap, mint, or DeFi interaction).
- **Value:** the amount of native coin sent. Token transfers appear in a separate "token transfers" section.
- **Gas:** fee paid, and gas price at the time.
- **Block and timestamp:** when the transaction was confirmed.
- **Input data:** for contract interactions, the function called and its parameters (decoded on most explorers if the contract is verified).

Practice: pick any transaction hash from a project's announcement and read it on the explorer until each field makes sense. This skill alone prevents many scams — you can verify claims instead of trusting them.

## 4. Wallets and addresses: what you can and cannot learn

What you can learn:

- An address's balance, transaction history, and token holdings.
- Whether an address interacts with known contracts (exchanges, DeFi protocols, NFT markets).
- Patterns: accumulation (steady buying), distribution (steady selling), or dormancy.

What you cannot reliably learn:

- **Who owns an address.** Labels from analytics firms are educated guesses, sometimes wrong, and sometimes planted.
- **Intent.** A large transfer to an exchange might mean selling — or it might mean custody, collateral, or an internal move. Exchange deposits do not automatically mean dumps.
- **A single person's full position.** One person can split funds across dozens of addresses.

**Rule:** treat address labels as hypotheses, not facts, and never make a trading decision on a single labelled transfer.

## 5. Holders and supply: concentration matters

For any token, check:

- **Total supply vs circulating supply:** total includes locked, reserved, or not-yet-issued tokens. Circulating is what can actually trade today. A token with a small circulating supply and a huge locked supply faces future selling pressure when locks expire.
- **Top holders:** if the top 10 wallets hold 80% of supply, a few decisions can move the price violently. If the largest holder is a burn address, a pool, or a vesting contract, that is different from a team wallet — read the labels and verify them.
- **Holder growth:** steady growth in the number of holders suggests widening distribution. Sudden spikes can be airdrops, bots, or Sybil addresses (many fake addresses controlled by one actor).
- **Exchange balances:** large, rising exchange balances are often read as selling pressure (coins moved to exchanges to sell), and falling balances as holding. This is a tendency, not a law — exchanges also move coins internally for custody and operations.

## 6. Flows: exchange, whale, and network activity

### Exchange flows
- **Inflows:** coins moving into exchanges. Often interpreted as intent to sell, but also happens for custody, lending, and internal reorganisation.
- **Outflows:** coins moving out of exchanges. Often interpreted as accumulation into self-custody, but also happens for exchange operations.
- **Net flow** (inflows minus outflows) is more informative than either alone, and still only a tendency.

### Whale activity
Large holders ("whales") are watched because their trades can move markets. But:

- Whale transactions are often split, routed through intermediaries, or executed over the counter (OTC), so what you see on-chain is partial.
- Copying a whale's visible move without knowing their full position, hedge, or intent is guessing, not strategy.

### Network activity
- **Active addresses:** how many distinct addresses transacted in a period. Rising activity suggests growing usage; falling activity suggests cooling interest. Bots and airdrop farming inflate this metric.
- **Transaction count and volume:** total activity, and the value moved. Distinguish count (many small transactions) from volume (a few huge ones).
- **Fees:** rising fees usually mean rising demand for block space. Persistently high fees can also push users to other chains.

## 7. Metrics beginners meet (and their limits)

| Metric | What it claims | Limit |
|---|---|---|
| NVT ratio (market cap / transaction volume) | Whether a network is overvalued relative to usage | Sensitive to how "volume" is counted; spam inflates volume |
| MVRV (market value / realised value) | Whether holders are on average in profit | Averages hide distribution; long-term holders and new buyers differ hugely |
| SOPR (spent output profit ratio) | Whether coins being moved are sold at a profit or loss | Only covers coins that moved, not all holders |
| Realised cap | Value of coins at the price when they last moved | Better than market cap for some purposes, but still an aggregate |
| Exchange reserves | Coins held on exchanges | Exchange labels are incomplete; internal moves look like flows |
| HODL waves | Age distribution of coins (how long since each coin last moved) | Old coins are not necessarily "strong hands" — they may be lost keys |

Use metrics as context, in combination, never as a single buy or sell signal.

## 8. On-chain analysis for safety: verifying projects

On-chain data is most valuable as a verification tool, not a trading signal:

1. **Verify the contract address** against the project's official channels, then read the contract on the explorer. Is it verified? Does it have dangerous functions (unlimited minting, owner-only drains, pausable transfers)?
2. **Check the deployer and owner wallets.** Did the team keep admin keys? Can they change the rules after launch?
3. **Check liquidity.** Is trading liquidity locked, burned, or controlled by one wallet that could remove it (a rug pull)?
4. **Check holder concentration and vesting.** Are team and investor tokens locked, and when do they unlock?
5. **Check actual usage.** Does the protocol have real, sustained transactions from many distinct addresses, or a burst of bot activity around launch?

If a project fails these checks, no price chart can rescue it.

## 9. Common mistakes

| Mistake | Better approach |
|---|---|
| Treating a labelled address as a known person | Treat labels as guesses; verify independently |
| Reading one large transfer as a definite sell | Look for confirmation: repeated flows, price action, and context |
| Ignoring bots and Sybils in address counts | Ask whether activity is real users or farmed activity |
| Using a single metric as a signal | Combine several metrics, and combine on-chain with fundamentals |
| Assuming transparency means safety | Public data can be manipulated: wash trading, fake volume, and misleading labels are common |
| Sharing your own addresses publicly | Anyone can then track your entire on-chain history — consider privacy before posting an address |

## 10. A beginner workflow

1. Pick one token you already hold or are researching.
2. Find its contract on the explorer from the project's official site.
3. Read: total supply, circulating supply, top 10 holders, and recent transfers.
4. Find one large transfer and trace it: where did it come from, where did it go, what contract did it interact with?
5. Write down, in plain language, what you actually verified and what you are still guessing.

Repeat this for a few tokens. The skill of reading a chain is worth more than any single dashboard.

## 11. Frequently asked questions

**Is on-chain analysis the same as technical analysis?**
No. Technical analysis studies price and volume history. On-chain analysis studies the blockchain's own records: transactions, holders, and flows. They complement each other.

**Can on-chain data predict prices?**
No, not reliably. It can describe current conditions and historical behaviour, but markets react to news, regulation, hacks, and human decisions that no on-chain metric foresaw.

**Is my on-chain activity private?**
Mostly no. On public blockchains, your transactions are visible to anyone who knows your address, and addresses can sometimes be linked to identities through exchanges, posts, or leaks. Privacy chains and mixing tools exist, but they carry their own legal and security risks.

**Do I need paid tools to start?**
No. Block explorers are free and are the most important tool. Start there before paying for dashboards.

> Educational content only. This is not financial, investment, or tax advice.
