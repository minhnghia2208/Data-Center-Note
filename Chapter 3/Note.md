# Hardware Building Block
## Cost-efficient server hardware
    - Cluster of low-end servers is more cost-efficient than high-end servers because low-end server shares a lot of components with mass-market comptuer. Thus, it's beneficial from economies of scale

    - The impact of large SMP communication efficiency:
        - Communication between multiple nodes of **shared memory** is 10^-6 secs
        - Communication with node of **shared memory** is 10^-9 sec
        - Communication time from 1 -> 2 nodes is large, but from 2 -> n nodes is minimal
        - High-end SMP servers (128 cores) vs Low-end SMP servers (4 cores):
            - High-end is faster individually
            - Performances are comparable in WSCs where massive amount of servers are connected
    
    - Brawny vs Wimpy servers
        - Why not use even smaller CPUs?
            - There is a sweetspot for how small/cheap CPU can be because of:
                - Load-balancing can become unpredictable.
                - Tail-latency can become a problem.
                - It becomes increasingly difficult to handle serialization and communication overhead
            - As a result, using smaller/cheaper CPUs drives down hardware cost, but increases software development cost
            - Networking requirement can be a problem. As we need more switches, connecting fabric which offset the saving cost of cheapper CPU
        
        - As the moment, the sweetspot of server for large-scale services is lower-end server class (overlap which high-end personal computer)
    
## WSC Storage
    There are 2 main types of data in WSC:
        - Private data:
            - Store in local in-memory, DRAM, or disk
            - This data is simple, doesn't require durability or replication
        - Shared data:
            - Must be durable
            - Accessed by large number of clients
            - Require complex distributed storage system

### Interplay of Storage and Networking Technology
- Networking vs Disks:
    - Network technology is becoming so good that locality of **Disks** within WSCs is no longer a concern
- Networking vs Flash:
    - Falsh perfomance is x100 times faster than disk, thus locality still matters

### WSC Networking