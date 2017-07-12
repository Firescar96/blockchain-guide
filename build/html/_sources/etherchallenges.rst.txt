===================
Solidity Challenges
===================
These challenges are designed to help you become comfortable as a smart contract developer. They are loosely arranged in order of difficulty. These challenges are not scored, it's up to you to determine when you have sufficiently completed them.

You may need the `resources from the previous section <./ethereum.html#interacting-with-your-contract-resources>`_ to complete these challenges.

1. download testrpc and go-ethereum and succefully install them
2. generate a new address using the geth console
#. check your account balance (web3.eth.getBalance(<your account>))
#. send 5ETH to the 0x0 address

  a) Hint: if you use the right blockchain you’ll have plenty of ETH

#. create a constructor for a contract that initializes a uint32 variable and create getter and setter functions for that variable.
#. install truffle and use its 'init' command to create a demo app
#. call a the getter and setter functions you created earlier by adding your contract to the Truffle dev environment and using the Truffle console
#. successfully initialize Web3 in the browser by hijacking the js console on https://ethereum.github.io/browser-solidity
#. use Truffle to get a contract abi and address and call a function of the contract using the web console
#. write and compile a very basic smart contract that forwards funds to another address
#. multi contract interaction

  a) write a "Ticker" contract with functions that convert between KES and ETH
  b) write from scratch or modify the ERC20 token standard to create a token that uses the Ticker contract to return a user's balance in KES

#. implement a function that can handle array deletions by shifting following elements to the left when an array element is deleted
#. create a web interface corresponding to a function in a contract, implementing an "ethereum faucet" allowing a user to input an address into a textbox and click a button to get free eth
