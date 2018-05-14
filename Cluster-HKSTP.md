# Cluster Configuration for HKSTP

We have 2 GPU servers, 5 storage servers and 5 General CPU servers in HKSTP. All servers are connected to one Mellanox 16 port 100Gbps Ethernet switch

# Switch comfiguration

* port 1-2 are connected to GPU0-1.

* port 3-7 are connected to CPU0-4.

* port 8-12 are connected to Storage servers. 

* port 13 is reserverd.

* port 14-16 are connected to Storage servers (Storage internal network).

port 1-13 are put in one vlan (untagged) while port 14-16 are put in another vlan (untagged).
