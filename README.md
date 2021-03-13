![TronPunks](/punk-variety.png)

## TronPunks: Collectible Characters on the Tron Blockchain

TronPunks are 10,000 unique collectible characters with proof of ownership stored on the Tron blockchain. No two are exactly alike, and each one of them can be officially owned by a single person as managed and verified by a contract running on the Tron blockchain. You can see which punks are still available along with some more general information over at https://tronpunklabs.com/


Once you are watching the contract you can execute the following functions to transact punks:

* ```getPunk()``` to claim ownership of a punk.
* ```transferPunk(address to, uint index)``` transfer ownership of a punk to someone without requiring any payment.
* ```offerPunkForSale(uint punkIndex, uint minSalePriceInWei)``` offer one of your punks for sale to anyone willing to pay the minimum price specified.
* ```offerPunkForSaleToAddress(uint punkIndex, uint minSalePriceInWei, address toAddress)``` offer one of your punks for some minumum price, but only to the address specified. Use this to sell a punk to a specific person.
* ```enterBidForPunk(uint punkIndex)``` enters a bid for the punkIndex specified. Send in the amount of your bid in the value field and we will hold that ether in escrow.
* ```acceptBidForPunk(uint punkIndex, uint minPrice)``` to accept a pending bid for the specified punk. You can specify a minPrice in Wei to protect yourself from someone switching the bid for a lower bid.
* ```withdrawBidForPunk(uint punkIndex)``` will withdraw a bid for the specified punk and send you the ether from the bid.
* ```buyPunk(uint punkIndex)``` buy punk at the specified index. That punk needs to be previously offered for sale, and you need to have sent at least the amount of Ether specified as the sale price for the punk.
* ```withdraw()``` claim all the Ether people have previously sent to buy your punks.

### Verifying the Punks

![All the TronPunks](/punks.png)

To allow verification that the punks being managed by the TronPunks Tron contract are the same as what you see in the image, we have embedded a SHA256 hash of the image file into the contract. You can generate this hash for the punks image file via a command line similar to ```openssl sha -sha256 punks.png``` and compare that to the embedded hash in the contract ```ac39af4793119ee46bbff351d8cb6b5f23da60222126add4268e261199a2921b```.
