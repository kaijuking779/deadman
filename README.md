# deadman

The purpose of this project is to create an ethereum contract that other contracts can
use to check if a wallet address is still active.

This is done onchain by mapping a wallet address to a timestamp which can be queried
by other contracts. One of the key factors is that anyone can update the timestamp.
This is because this contract serves as a LAST RESORT to ownership transfers and should
be *difficult* to trigger. We also want this contract to last a very long time so every
timestamp is not saved in seconds but days since contract was deployed. Given that a storage
slot is 32 bytes, even 2 bytes would give us 200 years.

Since this contract is of last resort, we don't need to worry about gas cost of external calls.
We also reduce gas cost by allowing anyone to update and any contract to access onchain.
