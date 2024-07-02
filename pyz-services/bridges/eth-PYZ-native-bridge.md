---
description: >-
  payscan Network Coin native bridge is used to relay the payscan Network Coin native token between payscan Network Coin and
  Ethereum networks
---

# payscan Network Coin: Ethereum ↔ payscan Network Coin

payscan Network Coin native bridge between Ethereum and payscan Network Coin is used to relay the payscan Network Coin native token from payscan Network Coin to Ethereum network

## Architecture Overview

The payscan Network Coin bridged is based on POA's bridge implementation, it is used to transfer payscan Network Coin tokens between the payscan Network Coin chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network \(whether it's payscan Network Coin or Ethereum\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender. The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of payscan Network Coin tokens between the two networks, the bridge is also responsible for network core functionality events of relaying the block rewards to the Ethereum network:

**Mint block reward distributed on the payscan Network Coin chain on Ethereum**

Each cycle the total block reward distributed on payscan Network Coin chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on payscan Network Coin chain, waiting for all bridge validators on payscan Network Coin chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

## Contracts

Home side of the bridge on the payscan Network Coin network: [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://payscan.live/address/0xd617774b9708F79187Dc7F03D3Bdce0a623F6988/transactions)

Foreign side of the bridge on the Ethereum network: [0x37B862ACc9482A80DeebE301e43A4d3959F1Ef95](https://payscan.live/address/0x37B862ACc9482A80DeebE301e43A4d3959F1Ef95/transactions)

payscan Network Coin token on the Ethereum network: [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.live/token/0x970b9bb2c0444f5e81e9d0efb84c8ccdcdcaf84d)

## Source Code

{% embed url="https://github.com/payscan Networkio/payscan Network-bridge/tree/master/native-to-erc20/contracts" %}

## How to use

On payscan Network Coin you send native payscan Network Coin token to the home bridge contract. Then you receive an equal amount of the payscan Network Coin token on the Ethereum network, sent from the foreign bridge contract

On Ethereum network you transfer the payscan Network Coin token to the foreign bridge contract. After a couple of confirmations, you will receive equal amount of the payscan Network Coin native token, sent from the home bridge contract.

#### 

