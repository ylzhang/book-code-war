# Chapter 10.5: Another Possibility of Trust — Bitcoin and Cryptographic Verification

October 31, 2008. Halloween.

Satoshi Nakamoto sat in front of a computer, staring at the paper he had just completed.

In a cryptography mailing list, he wrote a paragraph:

> "I am developing a new electronic cash system, completely peer-to-peer, without the need to trust a third party."

Attached was a 9-page PDF: *Bitcoin: A Peer-to-Peer Electronic Cash System*.

**Why do this?**

Two months earlier, Lehman Brothers collapsed. The global financial crisis erupted; governments used taxpayers' money to bail out banks, while ordinary people lost their jobs, homes, and pensions.

Satoshi pointed out the problem in the first paragraph of the whitepaper:

> "Commerce on the Internet has come to rely almost exclusively on financial institutions serving as trusted third parties to process electronic payments."

The problem is: these third parties are not trustworthy.

Satoshi's solution is simple: **remove the third party**.

No need for Alipay, no need for banks, no need for any intermediary. Two people transact directly; cryptography ensures security, and consensus mechanisms ensure fairness.

This is the core of Bitcoin: trust does not come from institutions, but from mathematics.

---

January 3, 2009. The Bitcoin network officially launched.

Satoshi mined the first block—the Genesis Block. He left a message in the block:

> "The Times 03/Jan/2009 Chancellor on brink of second bailout for banks"

**Bitcoin is a rebellion against the traditional financial system.**

---

**Meanwhile, on the other side of the Earth.**

May 22, 2010. Florida.

Programmer Laszlo Hanyecz posted on the Bitcoin forum:

> "I will pay 10,000 Bitcoins for two large pizzas."

This is the first physical transaction in Bitcoin history.

Calculated at later prices, these two pizzas are worth hundreds of millions of dollars. They are called "Bitcoin Pizzas," and every year on May 22, the community designates it as "Bitcoin Pizza Day."

This is another form of trust.

In traditional e-commerce, buyers and sellers do not trust each other and need Alipay as a guarantee. In Bitcoin transactions, both parties also do not know each other, but no intermediary is needed.

**Why?**

Because code is law. Once a transaction is written into the blockchain, it is immutable, irreversible, and globally visible.

No need to trust the other party; just trust cryptography.

---

Let's delve into the technical core of Bitcoin.

Each page (block) records all transactions over a period of time. At the end of each page, there is a special number—it is calculated from the content of the previous page.

If you tamper with any content on the previous page, this number will change. The next page will detect this change and refuse to recognize the legitimacy of this page.

This is the blockchain.

The generation of each page (block) requires solving a mathematical puzzle. This puzzle has no shortcuts; it can only be solved by brute force calculation. Whoever solves it first has the right to write this page and receives a reward (newly issued Bitcoins).

This process is called "mining."

Solving the puzzle requires consuming large amounts of electricity and computing power. If an attacker wants to tamper with history, they need to recalculate all the puzzles from that block to the present, requiring computing power exceeding 50% of the entire network.

**This is Bitcoin's security model: not from institutional credit, but from the game of computing power.**

But this design has a cost: **slow**.

Bitcoin can only generate one block every 10 minutes, and each block can only accommodate a few thousand transactions. Compared to Alipay processing hundreds of thousands of transactions per second, Bitcoin is as slow as a snail.

Moreover, mining consumes enormous amounts of electricity.

This is the cost of decentralization. If you don't want centralized institutions, you need to use computing power to replace trust; if you use computing power to replace trust, you need to consume energy.

**Bitcoin chose the minimization of trust, even at the cost of maximizing inefficiency.**

---

The earliest Bitcoin mining could be done with ordinary computers.

In 2010, someone discovered that mining with graphics cards (GPUs) was dozens of times faster than with CPUs.

In 2013, ASIC (Application-Specific Integrated Circuit) mining machines appeared. These are chips specifically designed for Bitcoin mining, with efficiency hundreds of times higher than GPUs.

Mining machines range in price from a few thousand to tens of thousands of dollars. Ordinary people can no longer participate in mining; mining has become a capital-intensive industry.

**This is the paradox of decentralization: theoretically everyone is equal, but in reality, it is monopolized by capital.**

Bitcoin's design is to remove intermediaries. But in reality, most people buy and sell Bitcoin through exchanges.

Coinbase, Binance, Kraken—these platforms have become new intermediaries.

The Bitcoin community scoffs at this: "Not your keys, not your coins."

But the reality is that most people choose convenience over autonomy.

**This is the paradox of human nature: theoretically pursuing freedom, but in reality choosing security.**

---

Bitcoin's foundation is cryptography, but its physical foundation is electricity.

The minting of every Bitcoin corresponds to real energy consumption.

Mining machines require large amounts of electricity and generate large amounts of heat. Mining farms are usually built in places with cheap electricity and cold climates.

Sichuan and Inner Mongolia in China once concentrated 70% of the world's computing power.

In 2021, the Chinese government banned Bitcoin mining. Computing power migrated on a large scale to the United States and Kazakhstan.

**Bitcoin mining has unexpectedly become a regulator of the power grid.**

The core of ASIC mining machines is chips. The more advanced the chip process, the higher the energy efficiency.

Bitmain's Antminer series has evolved from 28nm process to 7nm, 5nm.

But Moore's Law is failing. Below 5nm, quantum tunneling effects make chip design increasingly difficult.

Bitcoin mining is approaching the physical limits of silicon-based chips.

---

Looking back from 2026, Bitcoin and Alipay represent two extreme paths of trust.

**Alipay: Centralized Trust**
- There is a central node (Alipay) holding funds
- When there is a dispute, someone can arbitrate
- Efficient, convenient, user-friendly
- Cost: You must trust that central node

**Bitcoin: Decentralized Trust**
- No central node; code is law
- No dispute resolution mechanism; transactions are irreversible
- Inefficient, complex, high user threshold
- Cost: You must keep your own private key; if lost, it is permanently lost

Which path is better?

It depends on who you ask.

For ordinary people in Venezuela or Argentina, Bitcoin is a life-saving straw against inflation.

For Chinese online shoppers, Alipay is the infrastructure of daily life.

**Bitcoin and Alipay are not competitive, but complementary.**

They represent two different understandings of "trust":
- One believes in systems and institutions
- One believes in code and mathematics

And the truth may be: we need both.

The true meaning of Bitcoin is not to replace Alipay, but to provide a choice.

**When centralized trust disappoints you, you have another path.**

---

**December 17, 2017**. Bitcoin price reached an all-time high: $19,783.

From almost zero in 2009 to nearly $20,000 in 2017, Bitcoin completed in eight years what traditional assets took decades to achieve.

But behind this is violent volatility. In 2018, Bitcoin fell to $3,000. In 2021, it rose to $69,000. In 2022, it fell to $15,000 again.

This volatility makes Bitcoin difficult to become a daily payment tool, but it makes it a paradise for speculators.

**Five years later, 2022**: Terra/Luna collapsed, Three Arrows Capital went bankrupt, FTX exchange imploded. The greed of centralized institutions once again proved Satoshi's foresight.

**Ten years later, 2024**: The US SEC approved Bitcoin ETFs; traditional financial institutions began to embrace this former "rebel." Bitcoin seems to be moving from the fringe to the mainstream.

**Twenty years later, 2034**: When Central Bank Digital Currencies (CBDCs) become widespread, when all transactions are monitored by the government, will Bitcoin become the last bastion of privacy?

**Thirty years later, 2044**: When quantum computers crack existing encryption algorithms, will Bitcoin still exist? Can the code Satoshi left behind withstand technological iteration?

The destiny of code depends on the people holding the keyboard.

And the debate about trust will never end.