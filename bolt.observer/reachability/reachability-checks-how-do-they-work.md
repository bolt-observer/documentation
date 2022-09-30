# Reachability checks - how do they work

You can use any combination of checks for your node,limited only by connectivity options you have - ipv4, ipv6, tor.

**Lightning**

We send a small probe over lightning network to see if your node responds. Checks are run on multiple nodes positioned in different parts of the network to ensure connectivity and prevent false positive alerts.

**TCP**

Basic tcp check to see if your node is reachable on port 9735 over internet. Supports ipv4 and ipv6.

**Tor**

Basic tcp check to see if your node is reachable on port 9735 over Tor network.
