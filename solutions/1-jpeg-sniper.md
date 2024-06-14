## Solution

We see that there is one function that can be immediately called by the external user that it  [`publicSaleMint()`](../src/jpeg-sniper/FlatLaunchpeg.sol#L34) and we see that the CEI pattern is violated resulting in classical reentrancy though there is one more thing the contract checks is for it to be an `EOA` externally owned account but we can easily bypass that by calling all the necessary logic inside the constructor of the contract because the runtime logic is not yet stored and thus extcodesize returns `0`.

See the solution implemented [here](../test/1-jpeg-sniper.sol#L39) .

## Resources for extra knowledge
https://gus-tavo-guim.medium.com/reentrancy-attack-on-smart-contracts-how-to-identify-the-exploitable-and-an-example-of-an-attack-4470a2d8dfe4