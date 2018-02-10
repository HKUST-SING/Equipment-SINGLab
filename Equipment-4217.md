# Server List

| Hardware Model | Quantity | Label | Specification |
| :-------------: | :-------------: | :-------------: | ------------- |
| HUAWEI Tecal RH1288 V2 | 40 | 192.168.2.100-139 | [Link](https://www.anylinq.com/wp-content/uploads/2014/03/Huawei-Tecal-RH1288-V2-Rack-Server-Brochure.pdf) |
| SUPERMICRO# 118-20 | 4 | 192.168.2.200-203 | [Link](https://www.eximpulse.com/import-product-Supermicro-port-Cochin-Air-Cargo-ACC-hscode-84715000-country-FRANCE.htm) | 

Note: 

* The SuperMicro machines are equipped with 4 Nvidia Tesla K40m GPUs.

# Network Architecture

# Detailed Server List
| MGT IP | NVMe | GPU | NIC | NIC Port 0 | NIC Port 1 | Task |
| ------ | ---- | --- | --- | ---------- | ---------- | ---- | 
| 192.168.2.100 | - | - | Mellanox ConnectX 5 100G | Connect to Facebook Wedge32 port 1 via Mellanox 100G DAC Cable | - | Monitoring Task - Zhaoxiong |
| 192.168.2.101 | - | - | Mellanox ConnectX 5 100G | Connect to Facebook Wedge32 port 3 via Mellanox 100G DAC Cable | - | Monitoring Task - Zhaoxiong |
| 192.168.2.102 | - | - | Mellanox ConnectX 4 | 10.200.1.102 Connect to Leaf 0 port 1 via Mellanox 40G DAC Cable | - | Networking Test - Junxue & Jiacheng |
| 192.168.2.103 | - | - | Mellanox ConnectX 4 | 10.200.1.103 Connect to Leaf 0 port 2 via Mellanox 40G DAC Cable | - | Networking Test - Junxue & Jiacheng |
| 192.168.2.104 | - | - | Mellanox ConnectX 3 | TODO | Connect to Mellanox Switch port 1 via Mellanox 40G DAC Cable | Ceph Storage - Justin & Chaoliang |
| 192.168.2.105 | - | - | Mellanox ConnectX 3 | TODO | Connect to Mellanox Switch port 2 via Mellanox 40G DAC Cable | Ceph Storage - Justin & Chaoliang |
| 192.168.2.106 | - | - | Mellanox ConnectX 4 | 10.200.1.106 Connect to Leaf 0 port 3 via Mellanox 40G DAC Cable | - | Networking Test - Junxue & Jiacheng |
| 192.168.2.107 | - | - | Mellanox ConnectX 4 | 10.200.2.107 Connect to Leaf 1 port 1 via Mellanox 40G DAC Cable | - | Networking Test - Junxue & Jiacheng |
| 192.168.2.108 | - | - | Mellanox ConnectX 3 | TODO | Connect to Mellanox Switch port 3 via Mellanox 40G DAC Cable | Ceph Storage - Justin & Chaoliang |
| 192.168.2.109 ~ 192.168.2.128 | - | - | - | - | - | - |
| 192.168.2.129 | - | - | Mellanox ConnectX 4 50G | TODO | - | Ceph Storage - Justin & Chaoliang |
| 192.168.2.130 | - | - | Mellanox ConnectX 4 50G | TODO | - | Ceph Storage - Justin & Chaoliang |
| 192.168.2.131 | - | - | Mellanox ConnectX 4 50G | TODO | - | Ceph Storage - Justin & Chaoliang |
| 192.168.2.132 ~ 192.168.2.133 | - | - | - | - | - | - |
| 192.168.2.200 | - | 4 x Tesla K40m | Mellanox ConnectX 4 | TODO | TODO | - | 
| 192.168.2.201 | - | 4 x Tesla K40m | Mellanox ConnectX 4 | TODO | TODO | - | 
| 192.168.2.202 | - | 4 x Tesla K40m | Mellanox ConnectX 4 | TODO | TODO | - | 
| 192.168.2.203 | - | 4 x Tesla K40m | Mellanox ConnectX 4 | TODO | TODO | - | 


# Switch List
| Hardware Model | Quantity | Label | Specification |
| :-------------: | :-------------: | :-------------: | ------------- |
| Mellanox SN2100 | 2 (1 lent to NUDT) | - | MLNX 40/100G switches, 16 ports | 
| Accton AS7712 | 4 | - | Cumulus Linux; 100G, 32ports |
| Accton AS5712 | 1 | - | Not yet installed |
| Wedge32-BF (Barefoot Tofino) | 1 | - | ONL | 
| Facebook Wedge32 | 1 | - | ONL |

Note:

* The new switch is being tested and would be uploaded soon.

# Extra NIC List
| NIC | Quantity |
| --- | -------- |
| Mellanox ConnectX-4 Lx 50GbE one port | 1 |
| Mellanox ConnectX-4 Lx 25GbE dual port | 4 |
| Mellanox ConnectX-4 Lx 10GbE one port | 4 |

# Extra Cable List
| Cable | Quantity |
| ----- | -------- |
| Mellanox 56GB QSFP AOC | 2 |
| Mellanox 100GbE to 2x50GbE 3m DAC | 1 |
| Edge-core 10GbE SFP 3m DAC | 4 |
| Edge-core 100GbE breakout 25GbE 3m DAC | 1 |
| Edge-core 100GbE breakout 25GbE 3m AOC | 1 |
| Edge-core 40GbE QSFP 3m DAC | 4 |
| Edge-core 100GbE QSFP 3m DAC | 4 |

# Usage List
| User | Equipment (Label) | Date from | Purpose |
| :-------------: | :-------------: | :-------------: | ------------- |
| Gateway | 192.168.2.254 | - | Gateway |
| Yu's group | 192.168.2.120,122-125 | now-late Feb. |  Lent to prof. Weichuan Yu, ECE |
| GPU | 10.40.2.200-203 | - | IPs for internal usage. |

Note:

GPU IPs have the corresponding NICs connected to high speed switches.
* Please keep the usage list up to date.
