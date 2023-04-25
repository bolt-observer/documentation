# LiquidOps

LiquidOps is a comprehensive tool designed to streamline liquidity management in your Lightning Network node. By periodically retrieving data from your node, LiquidOps offers configurable alerting on your balances and channel status, empowering you to make informed decisions about your node's liquidity. With its user-friendly workflows, LiquidOps simplifies node and liquidity management by providing a solution to automate manual tasks at scale.

Features available for LND and core-lightning:

* alerting on liquidity events
  * node level inbound or outbound capacity alerts&#x20;
  * channel specific configurable inbound or outbound capacity alerts &#x20;
* alerting on channel status (active/inactive)
* alerting on channel closing or opening
  * node level alerting on new opened channels or closed channels&#x20;
  * channel specific alerts for closing&#x20;
* alerting on node sync to chain or graph
  * channel specific alerts for closing
  * Task automation with workflows
* Liquidity management with auto-swaps
  * Auto swap-in : restore outbound liquidity with swap-in(s)
  * Auto swap-out : restore inbound liquidity with swap-out(s)

{% content-ref url="../../readme/liquidops/getting-started.md" %}
[getting-started.md](../../readme/liquidops/getting-started.md)
{% endcontent-ref %}

{% content-ref url="../../readme/liquidops/setup-liquidops/" %}
[setup-liquidops](../../readme/liquidops/setup-liquidops/)
{% endcontent-ref %}

{% content-ref url="../../readme/liquidops/node-and-liquidity-automation.md" %}
[node-and-liquidity-automation.md](../../readme/liquidops/node-and-liquidity-automation.md)
{% endcontent-ref %}

###
