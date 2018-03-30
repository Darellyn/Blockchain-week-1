## Week 1 Project: VirtLotto

**Due:** {{PROJECT(1) | longdate}} at 10pm

**Overview**: Build a simple DApp that allows users to bet on which number will be selected by a random number generator (kind of like the lottery). 


## User Stories

The following user stories **must** be completed:

- The contract has one operation `pickNumber(uint number) payable`.
    - `pickNumber` should accept integer between 1 and 10 inclusive, and accept any amount of ether (minimum bet is `X` finney).
    - After `Y` calls to `pickNumber`, the contract will choose a random number.
    - `X` and `Y` are configurable in the constructor of the contract. 
    - The winner(s) get to keep all the money that has been pooled in the contract. If there is more than one winner, the prize money is split evenly. 
- Addresses are limited on the number of tickets. One address can only purchase a maximum of 4 tickets.
- Users should be able to pick numbers via a simple web interface. A sample `index.html` [can be found here](https://gist.github.com/chug2k/b591831d5d3d289f1798a5446e99d4ca). 

## Tips

- Creating a random number is a bit difficult. For this example, you can try using something like this:
```
function random() private returns (uint){
    return uint8(uint256(keccak256(block.timestamp, block.difficulty))%10);
}
```
- You can use the `require` keyword to check that your parameters are correct. 

## Advanced

The following advanced user stories are **optional**. You're not required to do these, but you will learn more from doing them:

- Make a "true" random number. A common example is [to use Oraclize](https://github.com/oraclize/ethereum-examples/blob/master/solidity/random-datasource/randomExample.sol). 
- Contract picks winner after 5 calls or 5 minutes, whichever happens first. To schedule calls, you might want to look into using the [Ethereum Alarm Clock](https://ethereum.stackexchange.com/a/87/20239). 
- Contract offers dynamic odds. Once a number is picked, the payout to the winners decreases and odds on others increase proportionally.

## Other Resources 
* [Solidity Docs](https://solidity.readthedocs.io/en/develop/) -- the official Solidity docs
* [Remix IDE](https://remix.ethereum.org/) -- official tool to write, test, deploy contracts
