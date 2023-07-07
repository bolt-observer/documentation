# Agent configuration: auto swaps

In this guide, we will explore how to configure the open-source agent to perform auto-swaps.

Triggers and actions are the main components of a workflow. Once a trigger is activated, the workflow executes swaps until your channel or node liquidity reaches the desired level. Refer to the flowchart below for a visual representation:

<figure><img src="../../.gitbook/assets/Graphs - Auto swap flowchart(1).jpg" alt=""><figcaption><p>Auto swap flowchart</p></figcaption></figure>

In addition to defining "target" and "threshold" levels in the GUI, as shown in [create-a-workflow-with-auto-swaps.md](create-a-workflow-with-auto-swaps.md "mention"), you can also set options in CLI when running the agent:

### Max and min swap amounts

* `maxswapsats` allows you to set the maximum swap amount in satoshis.
* `minswapsats` enables you to define the minimum swap amount in satoshis.

### Maximum number of attempts

To manage the number of swaps executed by your workflows, use the `maxswapattempts` parameter. This parameter sets the maximum number of swaps authorized to reach your target liquidity levels. For example, if `maxswapattempts = 10`, up to 10 consecutive swaps will be allowed.

### Fee limits

In a context of a congesetd mempool, it is quite useful to limit the cost or your operations. You can set the upper limit for the cost of a swap, including Boltz fees, off-chain fees, and on-chain fees by using `maxfeepercentage` option.&#x20;

For instance, setting `maxfeepercentage` to 1% ensures the total cost of an 8M sats swap never exceeds 80k sats.&#x20;

{% hint style="info" %}
This options is helpful when the mempool is congested and on-chain fees skyrocket.&#x20;
{% endhint %}

Here is an example of agent settings that enable auto swaps:

<figure><img src="broken-reference" alt=""><figcaption><p>Agent configuration CLI: auto swap</p></figcaption></figure>

For more details about auto swaps, please refer to the following link:&#x20;

{% content-ref url="../liquidops/integrations/actions/perform-auto-swaps/" %}
[perform-auto-swaps](../liquidops/integrations/actions/perform-auto-swaps/)
{% endcontent-ref %}

{% embed url="https://github.com/bolt-observer/agent/blob/main/plugins/boltz/README.md" %}
Agent configuration for Boltz plugin
{% endembed %}

For general information on the open-source agent, you can find all the details in our [GitHub repository](https://github.com/bolt-observer/agent).&#x20;



