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

## Platform Level Infrastructure
    - Kernel: 
        - An abstract layer between hardware and software
        - It handles I/O, manages resources (memory, processors)
        - Kernel is loaded into memory when computer is booting up, and is released when computer shuts down
    - Firmware:
        - Store in ROM
        - It gives devices instructions on how to start-up, communicate with other devices
## Cluster Level Infrastructure
    1. Resource Management:
        - Allocating resources/machines to given user/job
    2. Hardware abstraction:
        - Reliable distributed storage (Database)
        - Message passing
        - Cluster-level synchronization
    3. Deployment and Maintanence
        - Image distribution
        - Configure management
    4. Programming framework
## Application Level Infrastructure
    - It is better to have a general-purpose hardwares because of:
        1. Diverse requirements: There are many software requirements that require different specilized hardwares
        2. It is easier and faster to make better algorithm than updating hardware

## Monitoring Infrastructure
    - Service-level Dashboards:
        - Avoid server disruption
        - Health check alert should be fine tune so that it would not send false positive alert, and it would not send alert too late
    - Perforamce debugging tools or Distributed system tracing:
        - Identify performance bottleneck
        - Does not require real time feed back like Service-level Dashboards
        - There are two types of tools:
            1. Black-box monitoring systems
            2. Application/middleware instrumentation systems
    - Platform-level health monitoring:
        - Health check for the whole system (software + hardware)
        - Cluster-level infra and application-level software are designed to tolerate hardwares failures, only monitoring at software level can miss hardware problem. Thus, if a problem is accumulated unoticed, disruption might occurs

## Buy vs Build
    - Built:
        - Pros:
            1. Flexible, quick turn-around time
            2. Cost efficiency
            3. Simpler and faster since in-house services only solve what is needed
        - Cons:
            1. Require more software development
            2. Require mantainance

## Tail-tolerance
    - Tail-latency is the latency of slowest requests
    - When system is large enough, it's impossible to avoid performance variability
    - Dean & Barroso proposed a programming method that takes advantage of resource replication. This tail-tolerant technique delivers low tail-latency
