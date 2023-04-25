# Channel balance

### Requirements

To use this feature, you need to have LiquidOps enabled with [agent](https://docs.bolt.observer/readme/liquidops/agent-based-push) version 0.2.0 or higher or enrolled with macaroons.



### Description

Channel balance checks perform constant monitoring of your channels´ liquidity and report when the liquidity falls below a certain level. The liquidity is the available balance that can be sent across the channel in one direction as reminded here below (source [lnbook](https://github.com/lnbook/lnbook))

`Liquidity(NodeA) = balance(NodeA) - channel_reserve(NodeA) - pending_HTLCs(NodeA)`

The channel i_nbound liquidity_ is the amount of bitcoin that a node can receive through that channel.

The channel o_utbound liquidity_ is the amount of bitcoin that a node can send through that channel.&#x20;

Note: We make a difference between the inbound/outbound liquidity at a channel level and at a node level. The inbound/outbound liquidity of a node will be the sum of inbound/outbound liquidity of all its channels and can be monitored with [node-balance.md](node-balance.md "mention") trigger.

The channel balance trigger can be configured by selecting 2 parameters :

Liquidity type: Inbound or Outbound

Threshold: expressed in %

