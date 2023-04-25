# Perform Auto Swaps

### Purpose

The purpose of automatic submarine swaps is to keep your channels automatically balanced and ensure you can receive payments and send payments at any time.

### Introduction

Submarine swap is a special type of atomic swap between on-chain and off-chain funds. This means it does not bear counterparty risk. Either the swap will go through completely or nothing will happen. It works in a similar trustless fashion as payments on the lightning network via HTLCs (hashed time-lock contracts). In practice that means if the exchange is dishonest, your funds might get locked up a while, but you will not lose money.

In case of “regular submarine swap” you swap on-chain sats for sats on lightning that are sent to you, while “reverse submarine swap” means you pay an invoice and get sats on-chain.

There are two categories of swaps:

* Swap-out moves sats from a channel to an on-chain address by paying an invoice and receiving
* Swap-in moves sats from an on-chain address to a channel, by being pushed to your side.

### Swaps use cases

There are three common scenarios where submarine swaps can be used to address liquidity challenges in Lightning Network channels:

1. Low inbound liquidity: This occurs when you need to receive payments in Bitcoin on your Lightning Network node, but your channel does not have enough inbound liquidity for others to route payments to you. In this case, you can perform a reverse submarine swap (swap-out) pushing funds to the other side of the channel. The exchange then sends you on-chain funds, which you can use to open more channels on your node or transfer to a cold wallet.
2. Low outbound liquidity: This is the opposite of the previous scenario, where your node has funds on the other side of your Lightning Network channels, making it difficult for you to make payments through Lightning. To address this, you can make an on-chain transaction, and the exchange will pay your invoice, effectively "moving funds" back to you and refilling the channel, which is sometimes referred to as a swap-in.
3. Low channel inbound liquidity: Similar to the first scenario, but in this case, you only need to address specific channels that are important for your payment routing or have favorable fee schedules. This can also be resolved through a reverse submarine swap (swap-out) where you pay only through the specified channel(s) instead through any channel.

A submarine swap is initiated by an operator manually when the liquidity of a channel or node is too low. As illustrated below, there is always a delay between the depletion of the channel and the detection of that state, resulting in the channel being rendered unusable for a certain period of time.

<figure><img src="../../../../../.gitbook/assets/Graphs - Frame 1.jpg" alt=""><figcaption><p>Submarine swaps lifecycle</p></figcaption></figure>

### Auto swaps

An auto swap is a proactive action configured by a node operator in anticipation of potential liquidity issues in the future, aiming to restore liquidity to a predefined level. It is executed automatically when the specified trigger conditions are met. Unlike regular swaps that involve a fixed amount, auto swaps are designed to maintain a desired liquidity level as a reference. Auto swap can trigger multiple swaps to restore liquidity to the desired level, ensuring that the channel or node remains adequately funded. Here is an illustration of 2 auto swaps-out executed as soon as trigger is activated:

<figure><img src="../../../../../.gitbook/assets/Screenshot from 2023-04-25 17-28-57.png" alt=""><figcaption><p>Illustration of auto swaps-out</p></figcaption></figure>

#### Fees breakdown

* Bolt Observer doesn't charge any fees.
* Boltz exchange charges fees for swaps according to their fee schedule, which includes:
  * 0.2% of the amount for BTC to LN-BTC swaps
  * 0.4% of the amount for LN-BTC to BTC swaps
* Routing fees for sending funds over lightning and miner fees for on-chain transactions are also charged.
* On-chain fees (X sats/vbyte) depend on the current bitcoin network price and are estimated by Boltz to confirm transactions within a reasonable amount of time.
* For a submarine swap (BTC → LN-BTC), the fee is 170 bytes \* X sats/vbyte, in addition to the 0.2% of the amount and routing fees.
* For a reverse submarine swap (LN-BTC → BTC), there are multiple phases:
  * Lightning routing fees (max 0.1% of amount)
  * Boltz charges 153 bytes \* X sats/vbyte for the lock-up of on-chain funds
  * 138 bytes \* X sats/vbyte are needed for the transfer from the "lock contract" to your address.
* You can run bolt-agent with **`-dryrun`** to check what would be done without incurring any costs.

#### Fees control

The main limitation to consider is the fees. The `--maxfeepercentage` is set to 5% by default, which means that the agent will continue creating swaps until the total fees spent for rebalancing is below this threshold. This setting applies to a single rebalancing event, which may involve multiple swaps. If the workflow action is triggered again, such as when liquidity goes above the target and then falls below it again, another rebalancing attempt will be made with the full 5% "allowance". In the examples developed below, the 5% limit is never reached.Agent configurationAgent configuration

#### Fees calculation&#x20;

Auto-swaps can facilitate various use cases to restore inbound or outbound liquidity. Here are a fees calculation for different scenarios:&#x20;

{% content-ref url="use-case-auto-swap-out-for-a-50m-sats-channel.md" %}
[use-case-auto-swap-out-for-a-50m-sats-channel.md](use-case-auto-swap-out-for-a-50m-sats-channel.md)
{% endcontent-ref %}

{% content-ref url="use-case-auto-swap-out-for-a-2m-sats-channel.md" %}
[use-case-auto-swap-out-for-a-2m-sats-channel.md](use-case-auto-swap-out-for-a-2m-sats-channel.md)
{% endcontent-ref %}

{% content-ref url="use-case-auto-swap-in.md" %}
[use-case-auto-swap-in.md](use-case-auto-swap-in.md)
{% endcontent-ref %}

### Agent configuration

You can easily configure the liquidity threshold on [bolt.observer](http://bolt.observer/). Once configured, the agent will calculate the amount needed to be swapped in order to reach that threshold. To execute the calculated swaps, simply run the agent with the `--action` flag. If you want to simulate the swaps without actually executing them, you can use the `--dryrun` option.

In use cases described above,

All configuration options:

```jsx
--boltzurl value           url of boltz api - empty means default - <https://boltz.exchange/api> or <https://testnet.boltz.exchange/api>
--boltzdatabase value      full path to database file (file will be created if it does not exist yet)
--boltzreferral value      boltz referral code (default: bolt-observer)
--zeroconf                 enable zeroconfirmation for swaps (default: true)
--maxfeepercentage value   maximum fee in percentage that is still acceptable (default: 5)
--maxswapsats value        maximum swap to perform in sats (default: 0)
--minswapsats value        minimum swap to perform in sats (default: 0)
--maxswapattempts value    maximum number of individual boltz swaps to bring liquidity to desired state" (default 20)
```

* `-zeroconf` option allows you to disable relying on 0-confirmation transactions in the mempool, and instead wait for the transaction to be confirmed in a block for added security.
* `--minswapsats` and `--maxswapsats` are parameters that give you control over the size of swaps. By setting these values to 0 and in such case Boltz limits are used (lower limit 50k sats, upper limit 10m sats)

Boltz plugin CLI options:

```jsx
NAME:
   bolt-agent boltz - interact with boltz plugin

USAGE:
   bolt-agent boltz command [command options] [arguments...]

COMMANDS:
   submarineswap         invoke submarine swap aka swap-in (on-chain -> off-chain)
   reversesubmarineswap  invoke reverse submarine swap aka swap-out (off-chain -> on-chain)
   generaterefund        generate refund file to be used directly on boltz exchange GUI
   dumpmnemonic          print master secret as mnemonic phrase (dangerous)
   setmnemonic           set a new secret from mnemonic phrase (dangerous)

OPTIONS:
   --help, -h  show help
```

You can manually invoke a swap like this:

```jsx
bolt-agent boltz submarineswap --sats 100000
```

ID is reported so you can continue doing a swap also if application died in the middle.

Just add `--id -1337`where -1337 is the ID reported and swap will be resumed from where it stopped before.Agent configurationAgent configuration

