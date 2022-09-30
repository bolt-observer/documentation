# Guide

Prerequisites:

* RPC or REST reachable from our addresses (3.233.3.134, 54.173.247.208)

Our nodes are connecting from 3.233.3.134 and from 54.173.247.208, so make sure you have those IPs whitelisted and that they can access LND API. We support both gRPC (usually on TCP port 10009) and REST API (usually running on TCP port 8080), so either of them should be enough (we prefer gRPC though).

