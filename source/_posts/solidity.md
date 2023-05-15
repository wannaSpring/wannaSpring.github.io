---
title: Web3
date: 2023-05-11 12:47:37
tags: Web3, Blockchain,
---
# Blockchain and cryto
## Purpose of blockchain
with a blockchain we can decentralize where code runs and agree on the output
- there's no single owner of the code's execution
- - the code always run as a program.
- - the code transparently verifieable.
> the purpose of blockchain is to have a <b>network of computer agree upon a common state of data</b>.no person or organization can control this, erevryone should be able to practicipate in this process.

![Picsee-20230511130710.png](https://raw.githubusercontent.com/wannaSpring/snapshot/main/Picsee/Picsee-20230511130710mneUCe.png?token=ALJ6LARDGOBC6O75NYEU56DELR4D6)

## blockchain network

- blockchain: protocal connecting these machines.
- each machine or node will in the network will run code as it is writen.
- the blockchain will enforce these rules.
- since the program is enforced, it is called "smart contract".

## bitcoin 

- the first successful blockchain and crypto.
- but there was much research and attempts before it
- a lot of components were discovered today.

## how it works 

- proof of work - Security.
- mining the rewards - fiancial incentives.
- public key cryptography: Authenication.
- linked data structures: chronology.
- peer to peer connection: permissionless.
these components work together in concert.
decentralization emerges from a properly setup network

## Cryto

way before crytocurrences, there was cryto.
two important primitives for our purposes:
- crytographic hashes
- publick key crytography.

### hash function

hash: give me a input I'll give u a fixed size output
input can be any type of data: image, string, video.

### crytographic hash function
a crytographic hash is a function with these  properties:
- deterministic
- pseudorandom
- one-way
- fast to compute
- collsion resistant.
sha256 is one such function which provides 256 bit outputs.

### crytographic hash functions
two important use cases for hash functions for us:
- commitments(smart contract)
- proof of work

# digital signature
## symmetric key
same key on both sides.
communication security over an unsecured channels.
history
- military  
- - key:324, msg: cat, encrypted: dog.
example:
aes: advanced encrypted standard.
downside: bothside must have the key beforehand.

## Asymmetric key
one public key, the other private key.
public key signs (encrypted).
private key verifies. (decrypted)

commonly referred to publicKey crytography.

## publick key in web3
- users sign a transaction with their private key.
- user boardcasts the transaction to blockchain.
- blockchain nodes recover public key from signature from which the user's address is derived. 

## RSA & ECDSA
RSA based on publick key methonology. it's very easy to find the product of two prime numbers, yet extremely difficult to factor out those two prime numbers if you have the product

The ECDSA algorithm uses elliptic curves. It can provide the same level security as other public key algorithms with smaller key sizes, which is the reason it's become quite popular. It is the Digital Signing Algorithm used by Bitcoin, specifically the secp256k1 curve.


# proof of work and mining
## mining key points
1. mining is the process to create a block of transaction to be added to blockchain.
2. peers in the mining process are called 'miners'
- a. to network
- b. miners provide processing power to network to exchange for chance to get rewards.

mining has two main functions:
1. consensus machanism 
2. currency issuance

in a decentralized enviorment we always have those issues:
- how  do all nodes agree on what current and future state of users account balance and contract interactions is?
- who gets to add new blocks/transactions to a chain.how do we know any blocks added are 'valued'
- how we know all of these thing condinated without any central actor in place?

the solution of those is consensus mechanism

## consensus mechanism
consensus mechanism means comming to a general agreement. <b> blockchain consensus mechanism typically means that at least 51% of nodes are in agreement over the current global state of the network</b>.

the main consensus  mechanism rules for proof-of-work typically look like religious commandments:
- cannot double spend
- the longest chain will be the one the rest of the nodes accept as the one "true" chain, determined by a chain's cumulative work. also known as <b>nakamoto consensus</b>.

## mining algorithm
when a miner 'mines' a block, what does the miner actually do?
mining software continously hashes a block until a hash is fount that meets a target difficulty.

## nonce
```javascript
sha256("Hi Grandma! coolgrandma555@hotmail.com 0"); // f2d9e2…
sha256("Hi Grandma! coolgrandma555@hotmail.com 1"); // 4ee36e…
sha256("Hi Grandma! coolgrandma555@hotmail.com 2"); // c25e5c…
// keep on guessing, keep on guessing…
sha256("Hi Grandma! coolgrandma555@hotmail.com 424"); // 5552ab…
```
> 📖 The number that we're appending on the end of the message here is generally referred to as a nonce. We'll see how both Ethereum and Bitcoin make use of nonces in a few ways!

# blockchain structure

The image show three different ways of internet. the first way is centralized for trandional applications, if u want prove value, it decide by centre services. the second way is Decentralized, it always be missunderstanding to blockchain. but blockchain have a important way, it is peer to peer. so the last image shows blockchain.
![Picsee-20230512151717.png](https://raw.githubusercontent.com/wannaSpring/snapshot/main/Picsee/Picsee-20230512151717l6NMC5.png?token=ALJ6LAVM5B4V2TPXWKILYKTELXUDW)

thought challenges
Q: how do distributed p2p networks agree on what data is validated without a central administrator running the show?
A: Consensus machanisms
 - the bitcoins network decides validity of new data based on who is able to produce a  prove of work.

Q: how is the block hash calculate?
A: the hash function takes data as input and returns unique hashes.

Q: what is 'valid' hash?
A: A valid hash is meet certain requirements.
- block index is greater than last block index.
- block previous hash is equal to lastest block hash.
- block hash meets difficulty requirements.
- block hash is correct calculated.

# aka
ethereum: 以太坊
Blockchain: 区块链
Crypto： 加密
crytocurrencts: 加密货币
decentralized: 去中心化
bitcoin： 比特币，第一个基于区块链技术实现的加密货币
fiancial incentives： 金融奖励
mining the rewards： 挖矿
deterministic: 确定性
pseudorandom: 伪随机
collsion resistant: 抗碰撞
consensus: 共识，一个网络对数据的状态达成共识。
censorship：审查
bribe： 贿赂
drill home： 钻研
relatively travel：相对较小的
infeasible： 不可能
symmetric: 对称
digital signature: 数字签名
RSA: 非对称加密的经典实现
ECDSA： bitcoin采用的非对称加密算法
ether： 以太币
address： 交易发起方类似于ip, bitcoin 使用checksum and base58, ethereum is last 20 bytes of the hash of the public key.
Enforcement： 执行 
consensus rules： 共识规则
consensus mechanisms：协商一致
inter-changeable: 可互换的
cumulative: 积累型
nakamoto consensus： 最长的chain将是其他节点接受的一个真正的链，他是由一条链积累的工作所决定的。
txs: transactions.
pos: proof of stack, pos中，参与者需要持有一定数量的crytocurrency，参与记账过程，相比pow，pos不需要大量的算力
pow: proof of work，miners通过计算来添加txs和block，需要消耗算力。可以增加security of  blockchain
merkle root：默克尔根，用来验证和确认交易是否被篡改。
underlying: 底层
hashcash： Hashcash工作量证明功能由Adam Back于 1997 年发明，并建议用于反 DoS 用途
Byzantine General's Problem： 在p2p场景下，如何证明每个机器都是在工作的。
manipulate： 操作
Genesis Block: 第一个加入到区块链中的块，初始块
cost-effective: 成本效益
UTXO：Unspent Transaction Output
