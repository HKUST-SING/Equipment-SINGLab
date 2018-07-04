# Huawei Cluster IP allocation (purposed)

All the IPs referred are 192.168.2.0/24 range

| IP range | Usage |
| :---------------------: | :---------------------: | 
| 192.168.2.1 ~ 192.168.2.100 | DHCP reserved |
| 192.168.2.101 ~ 192.168.2.129 | IP for CPU nodes* |
| 192.168.2.151 ~ 192.168.2.179 | IPMI IP for CPU nodes | 
| 192.168.2.180 ~ 192.168.2.189 | IPMI IP for GPU nodes |
| 192.168.2.190 ~ 192.168.2.199 | IP for shared CPU nodes** |
| 192.168.2.200 ~ | IP for GPU nodes |
| 192.168.2.254 | Legacy NFS + LDAP node |
| 192.168.2.113 | Maas IP + Gateway |

\* These nodes can be allocated via MAAS
\*\* These nodes are equipped with NFS and LDAP for public access inside the group.