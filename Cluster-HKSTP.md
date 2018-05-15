# Cluster Configuration for HKSTP

We have 2 GPU servers, 5 storage servers and 5 General CPU servers in HKSTP. All servers are connected to one Mellanox 16 port 100Gbps Ethernet switch. We also have 1 node for login and 1 node for providing MaaS. All servers are connected to one MGT switch.

# Switch Configuration

* MGT port is connected to MGT switch port 37.

* Serial port is connected to MaaS server.

* port 1-2 are connected to GPU0-1.

* port 3-7 are connected to Storage servers.

* port 8-12 are connected to CPU0-4. 

* port 13 is reserverd.

* port 14-16 are connected to Storage servers (Storage internal network).

port 1-13 are put in one vlan (untagged) while port 14-16 are put in another vlan (untagged).

# GPU Server Configuration

Each GPU node is equipped with 4 NVIDIA 1080Ti GPU, 1 NVMe and 1 Mellanox 100Gbps dual port NIC. 

## Network Configuration:

IPMI ports are connected to MGT switch port 1-2 with IP adress of 192.168.10.1-2/16.

First Ethernet ports are connected to MGT swtich port 31-32. DHCP.

Mellanox Connect X4 NIC ports 0 are connected to Mellanox switches 1-2.

# Storage Server Configuration

## Network Configuration:

IPMI ports are connected to MGT switch port 3-7 with IP adress of 192.168.20.1-5/16.

First Ethernet ports are connected to MGT swtich port 26-30. DHCP.

Mellanox Connect X4 NIC ports 0 are connected to Mellanox switches 3-7.

Mellanox Connect X4 NIC ports 1 are connected to Mellanox switches 14-16 (if needed).

# CPU Server Configuration

## Network Configuration:

IPMI ports are connected to MGT switch port 8-12 with IP adress of 192.168.30.1-5/16.

First Ethernet ports are connected to MGT swtich port 21-25. DHCP.

Mellanox Connect X4 NIC ports 0 are connected to Mellanox switches 8-12.

# MaaS Server

MaaS server provides baremetal server as a service, DNS service and DHCP service.

## Network Configuration:

First Ethernet port is connected to MGT switch port 33 with IP address of 172.17.0.1/16.
The second Ethernet port is connected to MGT switch port 34 with IP address 192.168.0.1/16 (act as IPMI gateway if needed).

# Login Server

Login server mainly provides vpn service.

## Network Configuration:

First Ethernet port is connected to MGT switch port 35 with IP address of 172.17.0.1/16.
Second Ethernet port is connected to public network, DHCP. Port 22, 80, 1194 should be open.

