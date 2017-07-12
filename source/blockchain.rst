====================================
In depth about Blockchain Technology
====================================

Trust
=====
The only way to have objective trust in the state of the blockchain is to download and verify the entire thing from the genesis block to the head.

Chain Reorgs
============
A blockchain will *fork* into two chains regularly as it's possible for multiple people to release valid blocks simultaneously. These forks resolve quickly as eventually one of the forks gains more hashpower support and dominates. As nodes switch over to the fork with more hashpower any transactions that were confirmed in the orphaned fork but not in the majority fork will no longer be valid. This is why it's important to never accept a transaction as valid until it has been included in a block; has one confirmation. Every succeeding block after that increases the transactions confirmation count.

Types of Nodes
==============
Depending on the blockchain technology used there are multiple type of nodes a user might run.

**Full nodes** are the default type and are required for the network to operate as they store the entire history of the blockchain. A full node can verify the validity of any transaction by walking the blockchain and verifying the validity of all previous transactions. Any new node to the network that wants to sync to the current block must contact a full node.

**Pruned nodes** are full nodes configured to only keep a fixed number of blocks in history. This allows users who have space constraints to make a trade of between space and security. It is inherently less secure to use a pruned node, consider a node that only keeps one block at a time. That node won't be able to detect forks starting a blocks earlier than the one that it is holding. Additionally if the node accepts a block that doesn't end up being accepted by the network, then it will have to resync from the genesis block all over again.

**Light Nodes** are not secure as they only store block headers, or don't store the blockchain at all and instead make calls to other full nodes to verify blocks and transactions. A light node cannot verify transactions by walking the blockchain, instead it generates a probability that a transaction is valid based off of how many confirmations it has. At the same time, light nodes are necessary to interact with the blockchain using mobile apps, browser extensions, and other platforms which don't provide much storage space.

Private vs Public Blockchains
=============================
The line between a blockchain and a database is not clear. Blockchain based systems are less efficient than databases, but in exchange have stronger consistency guarantees and work in environments with mutual disinterested (untrustworthy) participants.

Failure Modes
=============

51% Attack
##########
If a single entity has more than 50% of the hashpower on a Proof of Work based system then they are statistically more likely to produce blocks than the rest of the network. This allows them to do other things, such as rewrite the blockchain to erase certain transactions from history. This is a risk even for entities that have large but below 50% hashpower.

Contentious Hardforks
#####################
Forks can be done deliberately, but without overwhelming community support the two resulting blockchains will diverge and become irreconcilable.


Consensus Algorithms
====================
Alternative systems exist, but most blockchains are based on Proof of Work (PoW) to ensure the network can come to consensus on one true version of history and deter attackers. All versions of PoW involve hashing some combination of random data and data from the desired block to be added to the blockchain, but exact implementation details vary.

- Bitcoin: `SHA256 <https://en.bitcoin.it/wiki/Block_hashing_algorithm>`_
- Ethereum: `Ethash <https://github.com/ethereum/wiki/wiki/Ethash>`_
- Dogecoin: `Scrypt <https://en.wikipedia.org/wiki/Scrypt>`_
- Sia: `Blake2b <https://github.com/NebulousLabs/Sia/blob/b3ef0cc99d070ba4ce3aa357f793c64b59d01336/doc/Consensus.md>`_
