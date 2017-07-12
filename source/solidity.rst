========
Solidity
========

`Beginner's Guide Smart Contract Programming Tutorial <https://www.youtube.com/watch?v=R_CiemcFKis&list=PLQeiVDgMaJcWnAZLElXKLZhS5a71Sxzw0>`_
  If you're having trouble getting started, this series of youtube videos will walk you through writing a variety of contracts, explaining syntax along the way.
|

Some things to be wary of when designing Ethereum smart contracts:

- In most cases you’ll want to disallow users from transferring negative amounts of money.
- Make sure that updates to the int/uint types don’t induce integer overflows
- Solidity cannot store floating point values (decimals). Solutions involve multiplying all values by 10^3 or 10^6 before division. Refer to the `docs <https://solidity.readthedocs.io/en/develop/types.html#rational-and-integer-literals>`_ for more details.
- As a courtesy to users do not let them accidentally send money to the default address `address(0)`. Check for this specifically in functions dealing with transfers to accounts.
- For the actual Ethereum Network (not TestRPC) function calls, contract creation costs gas. If you don’t send enough gas the transaction gets atomically rolled back and your gas is lost. If you send too much the extra gets refunded.
- Array deletions in solidity do not automatically left shift elements to fill the empty space, you have to write a function for that yourself.
- *tx.origin*- this function should never be used (except in rare specific cases). It breaks the paradigm of ethereum by distinguishing contracts from users and so disallows, for example, multisig wallet contracts from using your dapp.
