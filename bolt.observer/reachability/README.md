# Reachability

Reachability monitoring for your nodes. We run periodic checks and alert you if we're unable to successfully reach your node.

We can alert you on any events impacting reachability of your node and deliver that alert to you through your favorite method. List of supported integrations can be found [here](../integrations/).



### Reachability checks - how do they work&#x20;

You can use any combination of checks for your node,limited only by connectivity options you have - ipv4, ipv6, tor.

**Lightning**

We send a small probe over lightning network to see if your node responds. Checks are run on multiple nodes positioned in different parts of the network to ensure connectivity and prevent false positive alerts.

**TCP**

Basic tcp check to see if your node is reachable on port 9735 over internet. Supports ipv4 and ipv6.

**Tor**

Basic tcp check to see if your node is reachable on port 9735 over Tor network.
