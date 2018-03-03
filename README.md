# DumbCoin

Welcome to DumbCoin, the world's dumbest cryptocurrency (next to Tron).

DumbCoin was built from scratch in Python as a personal project.

In DumbCoin, the miner of the first block receives the entire money supply - which, as of this writing, is 21 Million DumbCoins.

There is only one type of node, and they can all do two things: send/receive DumbCoin and mine blocks.

Nodes mine their own block upon creating a transaction, and broadcast their new block via a gossip protocol.

This repo also includes the beautiful, and highly-insecure DumbCoin Wallet and Block Explorer.

Enjoy.

![DumbCoin Wallet](https://thumbs.gfycat.com/VapidAgreeableDevilfish-size_restricted.gif)


DumbCoin was spawned from Bradfield's cryptocurrency course. The initial assignments are included below.

<hr>

# Build a blockchain!

In this assignment, you'll be building a blockchain from scratch. You'll want to build a block class, and then a blockchain class that includes all blocks.

* Block
  - `content` (string)
  - `previous_hash` (string)
  - `nonce` (string/number)

* Blockchain
  - `blocks` (array)

I should be able to initialize your blockchain as `Blockchain.new("this is a string".split(" "))` and have it automatically create blocks, compute proof of work for each block, and chain them all together in a blockchain. You should also be able to append new blocks to this blockchain.

<hr>

# Putting it all together: your first cryptocurrency

It's time now to build our first cryptocurrency!

Naturally this is going to be a toy cryptocurrency and we're going to be cutting some corners. But our goal is to have a network of full nodes that are achieving consensus on the same blockchain.

Here are the recommended steps:

1. First, build out your blockchain from the blockchain assignment.
2. You'll want to adapt this blockchain to store transactions rather than random strings. I recommend creating a `Transaction` class, which includes a `from` (public key), `to` (public key), `amount` (int), and `signature` (string). Have each block contain one transaction for simplicity.
3. Make your blockchain validate that all of the transactions within the blockchain are valid—i.e., each transaction does not put any party into a negative balance. You'll want to start all blockchains with a genesis block that gives someone seed money to begin the chain.
4. Implement a fork choice rule. Given your current blockchain and a new blockchain, write a function that replaces the old blockchain with a new blockchain if it's longer than your current blockchain (and valid!)
5. Go back to your gossip protocol and adapt it to gossip blockchains rather than random messages. You may want to use a good marshalling library for your language to make it easier to serialize and deserialize your objects. Apply the fork choice rule to any message you receive.
6. Give each node a public key and private key. Give it an endpoint so that another node can query it for its public key.
7. Give each node a `transfer` endpoint, which will make it query another node for its public key, and then transfer that node some of its money.
8. See the blockchain in action!

That said, feel free to approach this in whatever way you feel makes the most sense.
