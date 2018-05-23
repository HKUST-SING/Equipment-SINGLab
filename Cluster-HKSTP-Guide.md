# HKSTP Cluster Guide

# Update
## 2018-5-24
1. The RDMA is *TOTALLY AUTOMATICALLY* configured (except for storage nodes). The driver will be automatically installed during OS deployment. PFC will be configured when you first log in the system. 

* The PFC will be enabled on priority group 3. L3 mode.

* The RDMA-CM tos will be set to 106.

## 2018-5-22
1. The RDMA interface has been renamed to rdma0 and rdma01 (except for storage nodes). You can now use ```ping rdma0.cpu01.maas``` to access the rdma interface.

2. The VPN has been updated to handle clients with frequently changing IP, which would be quite useful when the clientes are behind NAT, such as HKUST eduroam.

# Networking Policy

* By default, your local traffic will not be forwarded via VPN. Please do *NOT* set up any proxy/tunnel to use the bare mental machine as an Internet gateway.

* Please keep your VPN configuration at a safe place.

* Please do *NOT* change IP addresses of any machines. If you do want some other IP address, please contact the infrastructure team.

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

Please follow this [guide](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-16-04#step-12-install-the-client-configuration) to configure the VPN.

*Do not give your configuration file to others*, you login will be audited.

*Do not change the DNS settings,* OpenVPN will send the DNS configuration files to your local computer. You local computer uses this DNS to resolve the domain name in our cluster.

# BareMental as a Service (MaaS)

After establishing the VPN connection, you can open your web brower and visit [http://maas.maas](http://maas.maas) to access the MaaS dashboard. You can acquire machines, deploy or re-deploy OS for different nodes.

After login to MaaS for the first time, you are required to import a public key, which is used for ssh login.

*IMPORTANT:* You have to import your key before deploying the OS, the key will be written to OS during deployment.

![nodelist](https://github.com/HKUST-SING/Equipment-SINGLab/blob/master/nodes.png)

From nodes section of the dashboard, you can find available nodes based on your account permission. Such as ```cpu01.maas```, ```cpu02.maas```. On your local computer, you can directly use the domain name to access one machine, such as ```ping cpu01.maas```. The domain name ```{nodetype0x}.maas``` refers to the IP address in the MGT network.

The domain name can also be used among machines.

You do *NOT* need to manually configure the IP address for network interfaces. *All* IP addresses of *all* interfaces are configured automatically via DHCP. A DNS record will be inserted to DNS server for each IP. So, let's forget about the IP and use domain name directly. If you *DO* want to use IP directly, you can also do that. The IP will not change until you release the machine.

One user can acquire only one machine. After finishing the machine, the user should release the machine, which will erase the disk. 

For a group of people working together, we will create a group account and add mutiple public keys for different members. Team leader can also manage the machines by himself/herself.

# Access RDMA Network

As mentioned before, the hostname ```{nodetype0x}.maas``` refers to the IP address of the MGT network. How can we access the IP address of the RDMA network ?

![cpu01 interface](https://raw.githubusercontent.com/HKUST-SING/Equipment-SINGLab/master/CPU01%20interface.png)

Take ```cpu01.maas``` for example, the interface ```ens3f0``` is connected to RDMA (fabric-rdma) network. (You can check the Interfaces section of a node). 

You can use ```rdma0.cpu01.maas``` to access the IP assigned to the interface.

~~The OFED driver is not installed by default. Please download the driver from [Mellanox](http://www.mellanox.com/page/products_dyn?product_family=26) and install it by yourself.~~

~~*TODO: Will provide the OS image containing the driver later.*~~

# Configure PFC & ECN for RDMA Network

DSCP 24 25 26 27 28 29 30 31 are mapped to TC 3.

ECN is turned on for TC 3.

TC3 is mapped to priority group 3.

We use L3 PFC and PFC is turned on for priority group 3 on RDMA network.

Please refer to this [guide](https://community.mellanox.com/docs/DOC-2881) for configuration.

