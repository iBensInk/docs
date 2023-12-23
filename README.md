# Overview
BENS is a protocol standard set specifically designed for Layer2 blockchains, compatible with the Ethereum Virtual Machine (EVM), and focuses on the standardized creation and transaction processes of inscription tokens. With BNES, users can effortlessly create and manage their digital assets while ensuring the security and transparency of transactions.
Anyone can easily deploy their own tokens, as well as mint and trade them, on the [Bens.ink](https://bens.ink) platform. 

# Indexer
The BENS protocol has introduced a series of convenient and efficient indexing methods based on Ethereum Virtual Machine (EVM) technology, and also established a standard to reduce gas costs during transactions. It has already been adapted for networks including Ethereum mainnet, Scroll mainnet, and Mantel mainnet, with more networks being synchronized for adaptation.

In this protocol, each event is permanently stored in the Ethereum Virtual Machine (EVM) input using hexadecimal codes, ensuring the immutability of data on the blockchain. 

Moreover, to expedite the speed of index information retrieval, it is recommended to send events to the zero address when the transaction value is not zero. 
```text
0x0000000000000000000000000000000000000000
```
On the content, we use JSON, which is consistent with brc20, but due to the particularity of Ethereum, we need to add a prefix to match the type, so the content of the token inscription needs to be prefixed.
```text
data:application/json,
```
Followed by JSON, their events are: Deploy\Mint\Transfer\Proxy Transfer\Freeze Sell\Refund.

Here is a simple example:
```
Deploy
data:application/json,{"p":"bens-20","op":"deploy","tick":"ticker","max":"21000000","lim":"1000","cap":"10000","dec":"8","nonce":"10"}

Mint
data:application/json,{"p":"bens-20","op":"mint","tick":"ticker","amt":"1000","nonce":"11"}

Transfer
data:application/json,{"p": "bens-20","op": "transfer","tick": "ticker","nonce": "45","to": [{"recv": "${target address}","amt": "10000"}]}

Proxy transfer
data:application/json,{"p":"bens-20","op":"proxy_transfer","proxy":[{"tick":"ticker","nonce":"20","from":"${seller address}","to":"${marketplace address}","amt":"333","value":"0.001","sign":"0x000"}]}

Freeze sell
data:application/json,{"p":"bens-20","op":"freeze_sell","freeze":[{"tick":"ticker","nonce":"1690469437811","platform":"${marketplace address}","seller":"${seller address}","amt":"12.39","value":"0.001","gasPrice":"23488286508","sign":"0x00"}]}
```

# What is BENS-20
BENS-20 is an EVM-compatible token protocol, offering a low-cost token ecosystem for users without altering the existing infrastructure.

