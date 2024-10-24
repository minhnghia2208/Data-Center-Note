# Energy and Power Efficency
## Power Usage Effectiveness (PUE)
- Total power usage within Datacenter vs IT Power (computing and network equipment)
- Most losses come from cooling

## Server Power Usage Effectiveness (SPUE)
- Total power usage of server (including Fans, power supply, volatage regulator) / Power usage of computing components (CPU, RAM, Dist, motherboard, ...)

## Power that goes to electric components is used for computing work
- Low utilization has less efficency than high utilization
- This is why when there is light load, load should be distributed to all servers instead of having them idling
- It's hard to scale-down WSCs during low-traffic period because data resilience, and data replication

## Cause of Poor Energy Proportionally
- CPU consumes the most energy in a server
- Thus, optimizing CPU power usage is good, but optimizing other computing components such as RAM, Network switch, ... is also important

## Other causes
- Disk drive mechanism can be optimized for better energy consumption (smaller platter, more pointers, slower rotational speed)
- Networking and Switches propotional energy consumption is bad, and network usage of network is becomming more and more popular. Networking capture 10-20% power consumption

## Low-Power modes
- Low-power or inactive mode works great for Mobile devices but not for WSCs. It's because activing in-active mode add up some latency. In WSCs, conversion between 2 states happens too oftens.
- In addition, inactive-to-active mode requires more energy (for example: spinning up disk platter). Thus, low-power mode only makes sense if servers are idle more than minutes (which usually not happens in WSC)

## Role of Software in Energy Propotional
- When designing software, try to keep Energy Propotional in mind
- There are 2 key challanges:
    1. Encapsulation: abstract logic away from application developers
    2. Performance Robustness: perfomance should not be impact by Energy saving logic

## Datacenter Power Provisioning
- Mixing different workloads in a WSCs can reduce peak consumption, thus utilizing power oversupcription
- When doing power oversupcription, we need to have safety switch. For example: pause low priority task such as batch job to leave power for more important tasks

## Using Energy Storage for Power Management
- Use a back-up battery to provide energy in case of power usage spike
- This system is currently not deployed by any datacenter because it's difficult and costly to deploy

