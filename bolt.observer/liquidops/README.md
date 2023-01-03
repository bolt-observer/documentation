# LiquidOps

LiquidOps is a product aimed at helping you manage liquidity of your lightning node. We do periodic pulling of data through your nodes API and provide you with configurable alerting on your balances and channel status.



Features:

* alerting on liquidity events
  * node level inbound or outbound capacity alerts&#x20;
  * channel specific configurable inbound or outbound capacity alerts &#x20;
* alerting on channel status (active/inactive)
* alerting on channel closing or opening
  * node level alerting on new opened channels or closed channels&#x20;
  * channel specific alerts for closing&#x20;



### Data input

We have two ways to obtain needed data from your node to facilitate alerting, depending on your preferences and risk models

{% content-ref url="../../readme/liquidops/guide.md" %}
[guide.md](../../readme/liquidops/guide.md)
{% endcontent-ref %}

{% content-ref url="../../readme/liquidops/agent-based-push.md" %}
[agent-based-push.md](../../readme/liquidops/agent-based-push.md)
{% endcontent-ref %}

### Data and privacy

bolt.observer is a SaaS platform and as that it means that data will be shared with us. If you are using our [agent](../../readme/liquidops/agent-based-push.md) then you are in complete control what and how much are you sharing with us. You can specifiy which specific channels and how precise the data you share with us will be. Data you share with us as part of our LiquidOps product belongs to you and is used exclusively for your needs.&#x20;

Our agent is open source so you can review what is being done. For more detailed overview of how agent works please refer to its [repository](https://github.com/bolt-observer/agent).
