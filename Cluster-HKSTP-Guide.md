# HKSTP Cluster Guide

# Infrustructure Architecture

![arch](https://raw.githubusercontent.com/HKUST-SING/Equipment-SINGLab/master/HKSTP%20Arch.png)

* Gateway: Gateway provides VPN service for users to login to HKSTP Cluster. Reserve proxy and software LB will also be provided to delegate the internal traffic to the public (Not yet configured).

* MaaS Controller: MaaS controller provides the BareMental as a Service. Users can use its dashboard to acquire a machine, deploy OS on a machine and etc. . MaaS controller also provides DHCP and DNS service for the whole cluster.

* Rack Controller: Provide control for one specific rack.

* MGT network: The MGT network is for management purpose. We have two subnet:

1. ```172.17.0.0/16``` main MGT subnet for ssh login, copying files and etc..

2. ```192.168.0.0/16``` BMC subnet for power control, such as powering on/off a machine.

* RDMA network: The RDMA network provides 100Gbps network. We have two subnet:

1. ```10.0.0.0/16``` main RDMA subnet. All machines are connected to this subnet.

2. ```10.1.0.0/16``` storage internal subnet. Only few storage nodes are connected to this subnet.

For more information, please refer our [configuration details](https://github.com/HKUST-SING/Equipment-SINGLab/blob/master/Cluster-HKSTP.md).

# Login via VPN

Each user will be provided with his/her own OpenVpn configuration file.

Please follow this [guide](https://raw.githubusercontent.com/HKUST-SING/Equipment-SINGLab/master/HKSTP%20Arch.png) to configure the VPN.

*Do not give your configuration file to others*, you login will be audited.

*Do not change the DNS settings,* OpenVPN will send the DNS configuration files on your local computer. You local computer uses this DNS to resolve the domain name of different nodes in our cluster.

# BareMental as a Service (MaaS)

After establishing the VPN connection, you can open your web brower and visit [http://maas.maas] to access the MaaS dashboard. You can acquire machines, deploy or re-deploy OS for different nodes.

After login to MaaS for the first time, you are required to import a public key, which is used to login to nodes.

From nodes section of the dashboard, you can find available nodes based on your account permission. Such as ```cpu01.maas```, ```cpu02.maas```. On your local computer, you can direct use the host name to access one machine, such as ```ping cpu01.maas```. The hostname ```{nodetype0x}.maas``` refers to the IP address of the MGT network.

The hostname can also be used among all machines.

# Access RDMA Network
