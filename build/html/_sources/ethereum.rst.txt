========
Ethereum
========

An up to date technical description of Ethereum can be found in the `Ethereum whitepaper <https://github.com/ethereum/wiki/wiki/White-Paper>`_. Read this first for an explanation of what Ethereum is and how it uses blockchain technology.

The following is a collections of useful resources and suggestions. Skim through the sections and use it as a reference. The `next section <./solidity.html>`_ will go more in depth about how to actually write smart contracts.

Wallets and Interacting with the Ethereum Blockchain
====================================================
There are two broad categories of wallets for Ethereum.

Light Clients
  don't require you to download the blockchain. In exchange for this convenience is you have **zero anonymity**, someone is able to see and track all the data for every transaction you submit through them and directly link it to you.

- `Jaxx <https://jaxx.io>`_- multi currency wallet available as a chrome extension,  mobile and desktop app
- `Metamask <https://metamask.io>`_- chrome browser extension backed by Infura for managing ether

Full nodes
  let you manage coins, mine ether, and keep your own personal storage of the full blockchain. There are two main options

- `Go-Ethereum <https://github.com/ethereum/go-ethereum>`_ (geth)- golang implementation of a full ethereum node
- `Mist <https://github.com/ethereum/mist>`_- desktop wallet developed by the developers at the Ethereum Foundation
- `Parity <https://parity.io>`_- rust implementation of a full ethereum node

Setting up Development environments
===================================

You can play around with smart contracts using the `online compiler <https://ethereum.github.io/browser-solidity/>`_ but for actual development the following components are needed:

- A general Purpose or Ethereum Specific IDE

  - suggested: `Atom.io <https://atom.io>`_, `Sublime Text 3 <https://www.sublimetext.com/3>`_, Vim, Emacs, `Notepad++ <https://notepad-plus-plus.org>`_
  - anti-suggested: Eclipse, IntelliJ, Visual Studio
- A blockchain

  - For testing use `TestRPC <https://github.com/ethereumjs/testrpc>`_, a blockchain simulator.
  - to submit your contracts to the actual Ethereum Network you will need a full node (covered above).
- A compiler, testing, and deployment utility

  - recommended: Truffle_, a smart contract development framework
  - alternative: `Embark <https://github.com/iurimatias/embark-framework>`_

Once you start dealing with real money make sure you don’t accidentally deploy to the real Ethereum blockchain when you meant to deploy to a testnet. Only run one blockchain at a time by only running one type of node at a time. Truffle can help you with managing multiple deployments.

Solidity Basics
===============
Solidity is the primary language used for coding Ethereum smart contracts. A fair amount of progress in understanding the language syntax can be obtained by understanding knowing the following three constructs.

- `Types <https://solidity.readthedocs.io/en/develop/types.html>`_
- `Constructors and Functions <https://solidity.readthedocs.io/en/develop/structure-of-a-contract.html#functions>`_
- `Special Solidity Calls <https://solidity.readthedocs.io/en/develop/units-and-global-variables.html#special-variables-and-functions>`_

There are many more features of solidity that are well documented in the `Solidity Documentation <https://solidity.readthedocs.io/en/develop/>`_. Although extensive, everything is useful and should be read at least once.


Interacting with your contract - Resources
==========================================
The documentation for the following software is essential for developing smart contracts using the recommendations given above.

- `Solidity <https://solidity.readthedocs.io/en/develop/>`_
- Truffle_
- `TestRPC <https://github.com/ethereumjs/testrpc>`_
- `Web3 <https://github.com/ethereum/wiki/wiki/JavaScript-API#web3eth>`_
- `Bignumber.js <https://github.com/MikeMcl/bignumber.js/>`_


Security
========
Hacks are forever (TheDAO was a unique exception). Be careful because unlike fiat currencies there is no bank you can call to save you if you mess up.

- `Best practices <https://github.com/ConsenSys/smart-contract-best-practices>`_
- `Security Considerations <https://solidity.readthedocs.io/en/develop/security-considerations.html>`_
- `Solidity Bugs <https://solidity.readthedocs.io/en/develop/bugs.html>`_


Testing
=======
Truffle, Embark, and Chaithereum are developer frameworks for developing Solidity contracts. Tests for all three are written very similarly.


Extra Data
==========
If you would like, you can go *even more* in depth into Ethereum by reading `this community maintained wiki <http://www.ethdocs.org/en/latest/>`_.


.. _Truffle: http://truffleframework.com/docs/
