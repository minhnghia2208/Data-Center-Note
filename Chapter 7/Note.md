# Dealing with Failures and Repairs
## Software-based fault tolerance
- Fault-tolerated softwares:
    - Pros: We can use cheaper/less reliable hardwares to maximize cost efficency
    - Cons: Harder to implement

## Categorizing faults
- Fault Serverity ranking (decreasing in severity):
    1. Corrupted: data is corrupted, lost
    2. Unreachable: service is down, or unreachable
    3. Degraded: service is available but in degraded mode, aka service is getting slower
    4. Masked: failure occurs but is hidden by fault-tolerant soft/hard ware

- Ideally, all faults are masked and invisble outside of service provider

## Causes of Service-level Faults
![plot](./fault_distribution.png)
- Hardware fault doesn't happen a lot because of good fault-tolerant. Fault-tolerant is easier to implement if system is static independent (like all hardwares)

## Machine-level Failures
- Machine-level failures include all faults that cause servers to shut down
- Only 10% Machine-level failures is caused by Hardwares or firmware, the rest are caused by software, network connection

### What causes machine crashes?
- DRAM Soft-errors: majority of errors are recoverable. Only 1.3% of machines in Google got DRAM soft-errors per year.
- Disk errors: only happens on faulty disk

### Predicting Faults
- It is hard and expensive to predict failure
- WSCs software is already gracefully handle fault, thus if failure happens, the penalties is not high

## Repairs
- Effective (speed & quality) is important as equipment in repair is equipment not operating
- In WSCs, because of large number of low-level servers, server in repair doesn't have big impact. Thus, we don't need to quickly response to repair.
- Instead, we can do repair in batch, to increase technician efficiency
- Because of massive number of machines in WSCs, we can use machine learning to analyze data and diagnose faults.
- We use Google System Health to collect and analyze data

## Tolerating faults, not hiding them
- When fault happens, even though service tolerates it, fault must be highly visible to operators