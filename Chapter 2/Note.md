# 2.1 Datacenter vs Desktop
    - Pros of datacenter:
        - Parrellism: 1 process can be ran in different servers
        - Workload churn: Clients are abstracted away from servers. Thus, software can be frequently updated without interuptting users
    - Platform homogenity: All servers has same config, unlike desktop software where each desktop config is different

# 2.2 Performance and availability toolbox
    Some common methods that improve performance and availability
    - Replication: 
        - Performance and availability 
        - Work well for mostly read data
    - Reed Solomon codes:
        - Encode/decode method to preserve data integrity in case of loss in network
        - Availablity
    - Sharding:
        - Partition data in smaller pieces
        - Perforamce and Availability
        - Good for distributed app and Parrellism
    - Load-balancing: Performance
    - Health checking: Availability
    - Integrity checking:
        - Check for data corruption
        - Availability
    - Application specific compression: 
        - Compress data in DRAM is faster than seeking disk
        - Performance
    - Eventual consistency:
        - When an update is made in a distributed database, all nodes will eventually be updated. This means queries will be incosistent as first and eventually consistant later): Performance and availablity
        - Unlike Eventual Consistency Strong consistency may reduce app performace
        - Performance and Availability
    - Centralized controle:
        - Perforamce
    - Canaries:
        - Only send request to one (or a few server) for validation before send the request to all servers. This method avoids total catastrophy
        - Availability
    - Redundant execution and tail tolerance:
        - Refer to 2.8
        - Performance
        