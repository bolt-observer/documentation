# Explorer

[Explorer](https://bolt.observer/explorer) is a tool for exploring lightning network. It enables you to find nodes with various filters, anywhere channel sizes, distance (number of hops) from your node, fees etc.

Available filters:

* Fees
  * Incoming
    * Average Base Fee
    * Average Free Rate
    * Median Base Fee
    * Median Fee Rate
  * Outgoing
    * Average Base Fee
    * Average Free Rate
    * Median Base Fee
    * Median Fee Rate
* Channel capacity
  * Average Channel Capacity
  * Median Channel Capacity
  * Minimum Channel Capacity
  * Maximum Channel Capacity
* Number of Channels
* Minimum Channel Size Limit
* Maximum Channel Size Limit
* Total Capacity
* Connectivity
  * ipv4
  * ipv6
  * tor
* Hops to reference node
  * Reference node is an anchor point from which you can filter nodes by their distance from it, for example if you only want to see nodes that are further than 2 hops away.
* Latency
* Betweenness centrality
  * On the lightning network, payments can be routed through different paths and nodes. Betweenness centrality measures all shortest paths between two nodes on the network. The betweenness centrality is the number of these shortest paths that go through a given node.
* Eigenvector centrality
  * Eigenvector centrality is a relative measure of the influence of a node in the network. It is comparable to Google PageRank for nodes. Each time a node opens a channel with a peer, the eigenvector centrality score increases. The more connected your node is, the higher its score; if it connects to hubs that have themselves more connections, that will improve the score even more.
* Closeness centrality
  * Closeness centrality is the sum of all shortest paths to every other node in the graph. The more central a node is, the closer to the center of the graph, and the smaller the closeness centrality.


