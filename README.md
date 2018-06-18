# NodeJS blockchain

## Blocks

A block consist of the following attributes
       
| Attribute | Description |
|---|---|
| timestamp | a unique timestamp for the block |
| lastHash | the hash of the previous block |
| hash | the hash of the current block |
| data | the data of the current block |
| nonce | a one time value used to generate a `hash` with the same number of leading zero is the `difficulty` attribute |
| difficulty | the mining difficult of the block |

### Genesis block

Every blockchain starts with the “genesis block” this is a default dummy block to originate the chain.

## Transactions

A transaction consist of the following attributes

| Attribute | Description |
|---|---|
| id | a unique id for the transaction |
| input | |
| outputs | |
 
## Wallets

A wallet consist of the following attributes

| Attribute | Description |
|---|---|
| balance | wallets balance amount |
| keyPair | |
| publicKey | wallets public key and address|

## Proof of work

The proof of work used is based on [hashcash](https://en.wikipedia.org/wiki/Hashcash)

The `difficulty` is the number of leading zeros the `hash` just have in order for that block to be successfully mined.

The `nonce` starts at 0 and is incremented by 1 until a `hash` with the same number of leading zero as the `difficulty` attribute is generated.


### Dynamic difficult

The system will automatically adjust the `difficulty` as more miners are added to the blockchain.

The `difficulty` is changed based on the time taking to mine the previous block. If the time exceeds the block mining rate, the `difficulty` is decreased and increased accordingly.

The block mining rate is controlled by a constant defined in config.js, `MINE_RATE` represents the millisecond rate that blocks should be mined.


