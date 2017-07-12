=============================
Limitations of the Blockchain
=============================

Virtual Machines
================
Code has to run somewhere- code in the cloud is actually running on Google or Amazon's servers and code on the blockchain is actually running on some miner's servers. This is especially salient for blockchain technologies like Ethereum which boast Turing complete languages, but also applies to more basic languages like Bitcoin Script. The computational power of the network is limited by how fast computers on the network can do your operations.

Size
====
- the size of the blockchain trends upwards
- some portion of the network must store everything
Don't contribute to blockchain bloat. Data should be deleted from storage as soon as possible to mitigate contributing to the inexorable increase in the size of the blockchain. Some blockchain technologies, such as Ethereum, give a discount to smart contract operations that involve deleting data to incentivize self-regulation of data storage.

Latency and Consistency
=======================
In general I/O operations take a long time, but the time it takes for a transaction to get included into a block after being sent into the network can be orders of magnitude longer. After a transaction is forwarded into the network it gets held in memory by nodes and miners until it eventually gets dropped or included in a block. There is a *non zero* chance of a transaction getting lost needing to be resent. This has implications for user interfaces which need to display some sort of loading animation until the transaction has been confirmed and potentially timeout and resend the transaction. When using a permissioned blockchain the confirmation time will likely be much lower than a public blockchain, but due to the decreased number of nodes the risk of nodes failing and dropping transactions may be higher.

The point to remember is transactions are not final until they get included into a block.

Legality
========
Code is not law, and don’t let anyone tell you otherwise. Smart contracts are merely a reflection of some soft, squishy, malleable social process. For example: if you write some code that is supposed to release 25% of funds to party A and 75% to party B, but a bug causes the two parties to be flipped, that does not mean done is done and the transfer is complete. Likely there will be some attempt by party B to execute legal action to rectify the situation. Smart contracts and the blockchain in general are an additional resource, but not a replacement for other social and legal constructs like courts.

The World Outside the Blockchain
================================
Only data that is stored on the blockchain can be manipulated by smart contracts. The blockchain cannot hold the entire contents of the world so data must be brought into the scope of smart contracts in a credible way. In the context of smart contracts entities that can be trusted to inject data about the outside world into the blockchain are called oracles. For example: Nasdaq might act as a price oracle and manage a smart contract that provides conversion rates between different stocks.

Identity
========
Identity management is hard, although not impossible. By design there are an effectively infinite number of addresses that a person can generate to use as their public key, giving them the ability to assume as many identities as they would like. Even in permissioned blockchains where the identity of all the participants is known identity management may be difficult. There are two scenarios.

Determining Identities of consenting individuals:
  Eventually there will likely be one or more organizations who provide identity oracle services on various blockchains. Multiple oracles should be used to attest to a persons identity. Oracles can be used to attest to any of the components of an individual's identity that are currently being used: age, phone number, home address, driver's license, etc. The difficulty of that organizations providing most of these services do not exist yet.

Determining Identities of non-consenting individuals:
  Most cryptocurrencies are not anonymous. Notable exeptions are `Monero <https://getmonero.org/knowledge-base/about>`_ and `Zcash <https://z.cash/technology/index.html>`_ which use different schemes to obscure the identity of the participants in a transaction as well as the amount transacted.

Multiple identities are nice when testing smart contracts as it lets you represent multiple parties, but for production systems you’ll need to write your own smart contract to handle identify or work with an outside company specialized in developing identity oracle solutions.

In Ethereum smart contracts are to be treated as first class citizens. By design the system tries to make it difficult to determine whether some address is a human account or another smart contract, and generally it shouldn’t matter. For arbitrary addresses your code should treat both the same.
