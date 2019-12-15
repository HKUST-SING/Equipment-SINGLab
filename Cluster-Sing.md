# Server List

| Hardware Model | Quantity | Label | Specification |
| :-------------: | :-------------: | :-------------: | ------------- |
| Dell PowerEdge R320 | 60 | sing (kaicpu2); sing001-sing019; sing040-sing059; sing101-sing120 | [Link](http://www.dell.com/hk/en/business/p/poweredge-r320/pd) |

# Switch List

| Hardware Model | Quantity | Label | Specification |
| :-------------: | :-------------: | :-------------: | ------------- |
| Pica8 P-3295 | 6 | p3295_1-p3295_6 | 48\*1Gbps+4\*10Gbps; [Link](http://www.pica8.com/documents/pica8-datasheet-48x1gbe-p3290-p3295.pdf) |
| Pica8 P-3297 | 5 | p3297_1-p3297_5 | 48\*1Gbps+4\*10Gbps; [Link](http://www.pica8.com/wp-content/uploads/2015/09/pica8-datasheet-48x1gbe-p3297.pdf) |

Note: 

* Pica8 P-3297 cannot enable ECN.

# Usage List
| User | Equipment (Label) | Date from | Purpose |
| :-------------: | :-------------: | :-------------: | ------------- |
| Admin | p3297_1; p3297_2 | - | Gateway & Lab Website |
| Hao Wang | sing41,42,50,51,54,55,57,59; p3295_1 | 2019-4 | Project experiments |
| Cengguang Zhang | sing101 | 2019-8 | download data |
| Yiqing Ma | sing11、12、15、16、101、102、103、41、42 | 2019-8 | Training Model |
| Zilong wang | sing8, 9, 50, 51 | 2019-9 | project |
| Di Chai | sing17, 19 | 2019-10 | project experiments|

# Malfunction Record
| User | Equipment (Label) | Failure type | Failure Cause | Failure recovery |
| :-------------: | :-------------: | :-------------: | :-------------: | ------------- |
| XXX | sing101 | Break down | overheating by ML training | not recovered |
| XXX | sing102 | Break down | overheating by ML training | recovered |
| XXX | sing103 | Break down | overheating by ML training | recovered |


Note:

* Please keep the usage list up to date.
* Gateway IP: 143.89.191.114. Hostname: sing.cse.ust.hk.
* switch IP: 192.168.2.1.
* Please avoid the long time high CPU utilization.

