##################
Failure By Example
##################
These are some examples of Ethereum applications which serve as examples of both what not to do and how to recover from failure.

TheDAO
======
TheDAO has multiple problems with it's design, enough that multiple prominent members of the Ethereum community `called for a moratorium <http://hackingdistributed.com/2016/05/27/dao-call-for-moratorium/>`_ until it could be redesigned. The biggest problem that led to its demise is called a “reentrancy attack”. By design of Ethereum's Turing complete language contracts can call each other.

The attack involves exploiting this to make calls to a contract in a way the contract developer did not expect.
`This Vessenes article <http://vessenes.com/more-ethereum-attacks-race-to-empty-is-the-real-deal/>`_ has a full explanation of how the attack works. For someone who is not used to thinking in terms of blockchain based systems the bug is an easy one to make.

TheDAO ultimately failed and led to a large rift in the Ethereum community, further devolving into a split of Ethereum into two different blockchains and cryptocurrencies. `Ethereum <ethereum.org>`_ and `Ethereum Classic <https://ethereumclassic.github.io>`_.
`This Coindesk article <http://www.coindesk.com/dao-attacked-code-issue-leads-60-million-ether-theft/>`_ provides more details on the consequences of TheDAO's failure.

For a hands on example of how the DAO hack worked check out `this github project <https://github.com/joeb000/mock-dao-hack>`_.

Ethereum Naming Service (ENS) launch
====================================

The ENS is another project built on Ethereum that suffered problems after its first launch. Fortunately the developers took notes from the shortcomings of TheDAO incorporated a failsafes into their contracts.

The ENS incorporated smart contracts that could be upgraded or taken down. This was crucial in recovering from the bugs discovered after ENS was deployed. The root ENS smart contracts were under the control of seven keyholders, all public figures, four of whom were required to sign off on any upgrades and changes.

The ENS developers posted a detailed `postmortem <https://docs.google.com/document/d/1Xr6JELHHWb5ONl_WvJDmIwbfShTgWpMqiNRag2IdmLI/edit>`_ of the shortcoming of their smart contracts after the system was taken down.

After the solving the bugs discovered in the first launch the ENS team had `security audits <https://medium.com/the-ethereum-name-service/the-ens-audit-results-are-in-7d4ab3c4a6ca>`_ done by two independent and prominent Ethereum developers. Additionally the ENS team *made the results of the audits public*, contributing to the community knowledge pool on developing safe, secure decentralized applications.

Gnosis Token sale
=================
Be diligent about promoting your smart contracts. There is a lot of hype in the blockchain space and people who will fund you just because you mention “blockchain”, “Ethereum”, or “Initial Coin Offering (ICO)”. Don’t succumb to the temptation! Use caps to only accept as much money into your smart contract as is necessary for your project to run.
