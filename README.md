## Week 1 Project: VirtLotto

**Overview**: Build a simple DApp that allows users to bet on which number will be selected by a random number generator (kind of like the lottery). 

Time spent:  

## User Stories
 The following **required** functionality is completed:
 
- [x] User is able to pick numbers via simple interface
- [x] X & Y values are configured in the constructor of the contract
- [x] X value is a minimum bet
- [x] Y value is number of bets before results are selected
- [x] The contract has one operation `pickNumber`
- [x] `pickNumber` accepts an integer between 1 and 10 inclusive.
- [x] `pickNumber` can accept any amount of ether
- [x] the contract will select a random number after `Y` calls to `pickNumber`
- [x] each address gets only 4 tickets maximum
- [x] Winner(s) are able to keep and get all the money that has been pooled in the contract.
- [x] The money is split between winners if there is more than one winner.

## Tips

- [x] Create a random number and use the examples.
```
function random() private returns (uint){
    return uint8(uint256(keccak256(block.timestamp, block.difficulty))%10);
}
```
- [x] Use the `require` keyword to check if the parameters are correct.


## Advanced

The following advanced user stories are **optional**. You're not required to do these but you will learn more from doing them:

- [x] User is able to make a "true" random number that uses oraclize.
- [x] Contract are able to picks winner after 5 calls or 5 minutes and scheduled calls to look using Ethereum alarm clock.
- [x] A number is picked and able to pay out to winners that decreases and the odds on others increases proportionally.

## Note 
Describe any challenges in building this Dapp, was it easy or not?
## Other Resources 
* [Solidity Docs](https://solidity.readthedocs.io/en/develop/) -- the official Solidity docs
* [Remix IDE](https://remix.ethereum.org/) -- official tool to write, test, deploy contracts
