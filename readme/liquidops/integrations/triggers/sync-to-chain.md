# Sync to chain

### Requirements

To use this feature, you need to have LiquidOps enabled with [agent](https://docs.bolt.observer/readme/liquidops/agent-based-push) version 0.2.0 or higher or enrolled with macaroon.

### Description

This alert is designed to notify you when your node is not synchronized with the Bitcoin blockchain. This can happen when your node loses connectivity to the chain, which in turn prevents your lightning node from updating on-chain information.

The consequences of this issue are twofold. First, your node may not be able to open channels, which can affect your lightning network operations. Second, and more concerning, is the possibility that someone may have cheated on you without your notice. Typically, lightning nodes would send out penalty transactions as a remediation in such cases, but due to the bug, this couldn't happen. This means that if you didn't use a separate watchtower and didn't upgrade your lnd version in time, your channel partners could potentially steal BTC from you by publishing old states.
