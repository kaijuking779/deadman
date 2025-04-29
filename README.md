# deadman

The purpose of this project is to create an ethereum contract that other contracts can
use to check if a wallet address is still active.

This is done onchain by mapping a wallet address to a timestamp which can be queried
by other contracts. One of the key factors is that anyone can update the timestamp.
This is because this contract serves as a LAST RESORT to ownership transfers and should
be *difficult* to trigger (Think probate when the state seizes your property instead of inheritance/will/trust). 
We also want this contract to last a very long time so every
timestamp is not saved in seconds but days since contract was deployed. Given that a storage
slot is 32 bytes, even 2 bytes would give us 200 years.

Since this contract is of last resort, we don't need to worry about gas cost of external calls.
We also reduce gas cost by allowing anyone to update and any contract to access onchain.

The main purpose of this is to recognize the differences between the digital and physical world.
Although all things do perish eventually in the physical world, I would argue we lose just as
much in the digital world for the same reasons: taking things for granted.

One of the strongest cases for this contract is for NFTs. As the number of NFTs in a collection
decreases, it starts to lose it's diversity and ecosystem. Although we can argue a smaller
set might be better for a collection, it should be decreased using a burn mechanic instead of
"unexpected accidents of a collector" which has no meaning. Like launching gold into space just
to increase the price of gold.
