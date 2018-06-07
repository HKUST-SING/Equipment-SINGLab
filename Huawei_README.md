# On acquiring Huawei Machines.

## Introduction

This document discusses the procedure of acquiring servers, switches and NICs for Huawei testbed.

## Public machines

We will keep 4 CPU nodes with RDMA capability accessible by the legacy LDAP account. You can feel free to try any functionalities. Usage of GPU nodes are not yet finalized and all suggestions are welcomed.

## Using other machines in Huawei cluster

Other machines in Huawei cluster will no longer provide NFS (network file system), 
instead we manage the cluster through a tool named MAAS(https://maas.io/). 
To be concrete, the application procedure is as following:

- Read through the machine lists to learn about current occupancy.
- Send an email to "network manager" and clearly describe your needs, and the estimated time needed.
- Use the allocated machines to do your experiments.
- Backup all your experiment data on the storage node (currently the gateway).
- Release the machines on MAAS interface, which erases ALL data on these machines.
- Send an email again to the manager, claiming the usage is finished.

## What if there is no sufficient machines?

You can share allocated machines with other users, 
but in this case you need to collaborate with current machine owners, 
and manager is not in charge of this unless the machines are released.

## Using GPUs

GPU nodes are precious, in case you have project/testing related, please purpose them well in advance.

## Others.

Current network manager is Qinghe Jing ```qjing{at}{ustemail}```
