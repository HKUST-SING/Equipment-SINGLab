# Networking Test Plan (Draft)

## Per Rack Test

All tests should be carried out under Leaf0 of our AS7712 testbed

Should include links to the configuration files for each case

### Port Breakout Test

1. 100Gbps breakout to 2 * 50Gbps DAC cables

results: (should include connectivity, throughput, latency)

2. 100Gbps breakout to 4 * 25Gbps DAC cables

results:

3. 100Gbps breakout to 4 * 25Gbps AOC cables

results: 

### Congestion Test (no port breakout)

Due to the NIC and cable limitation, we can delay the high fanout configuration

1. Throughput (fanout is from 1:1 to 17:1)

results:

2. Latency (fanout is from 1:1 to 17:1)

results:

### Congestion Test (port breakout)

Due to the NIC and cable limitation, we can delay this 

1. Throughput (48 * 25Gbps to 1 * 100Gbps port)

results:

2. Latency (48 * 25Gbps to 1 * 100Gbps port)

results:

## Cross Rack Test 

### Congestion Test (no port breaktout)

We can temporarily disable one Spine to avoid the interfere of multiple paths

1. Throughput (fanout is from 1:1 to 3:1)

One endhost should be connect to leaf 1 while the others should be connected to leaf 0

results:

2. Latency (fanout is from 1:1 to 3:1)

One endhost should be connect to leaf 1 while the others should be connected to leaf 0

results:
