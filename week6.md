# Performance Evaluation

Below performance testing was conducted on the server via the SSH from the workstation. Each result is discussed below.

### Baseline Performance:

(inital testing to compare to)
<img width="896" height="569" alt="image" src="https://github.com/user-attachments/assets/c24fe5b1-1946-4a49-9284-ec78ccf0503c" />

### CPU Performance:

Below shows how the CPU Scheduling responds to workload,
the load average of the CPU increases 10x under stress when compared to baseline results above.
<img width="888" height="476" alt="image" src="https://github.com/user-attachments/assets/92e6dc24-b1ab-4c57-a784-7868cb85cdb8" />

### Memory Stress Test:

Memory usage increased during test, however it returned back to baseline after test.
This shows how the system handled memory pressure well.
<img width="895" height="488" alt="image" src="https://github.com/user-attachments/assets/8d5a9aac-64b1-4268-963f-a58de0d54cfd" />

### Disk I/O Performance:

Disk usage remained the same, no real persistent disk pressure.
Performance remained stable under pressure.
<img width="895" height="394" alt="image" src="https://github.com/user-attachments/assets/82d0a930-41e2-4aa8-96cb-27fe9f592968" />


<img width="919" height="416" alt="image" src="https://github.com/user-attachments/assets/40a3fb0d-12d0-448e-9f8b-6df81e45b3c9" />

### Network Performance:

Latency is consistenly low, showing the server is suitable for local network workloads

***Stress-ng:***
<img width="901" height="429" alt="image" src="https://github.com/user-attachments/assets/c8010a68-b928-4920-a986-5e08c2868ce7" />

***Ping:***
<img width="876" height="583" alt="image" src="https://github.com/user-attachments/assets/50960f0d-8999-452e-ade6-ebe6b7ff47ea" />


### Post Performance Baseline Results:

System recovered normally after stress tests.
<img width="877" height="541" alt="image" src="https://github.com/user-attachments/assets/1b8f44c3-348e-4933-854f-ecd61ce297b4" />

## Comparison Table:

|Metric |Baseline | Under Load | Observation|
|-------|---------|------------|------------|
|CPU Load Avg| 0.03 | 0.45 | Huge increase when CPU is stressed|
|Memory Used |511 MiB | increased during test | returned to baseline|
|Disk Usage | 51% | 51% | No major disk impact|
|Network Latency|~0.04 |~0.05ms | Quite stable & no packet loss|


# Conclusion:

Performance testing identified CPU utilisation as the main **bottleneck**, with load averages increasing significantly during CPU-intense workloads. Memory pressure also increase temporarily under stress, but returned quickly to baseline measurements. Disk I/O and network performance remained stable and didn't present any potential bottlenecks. 

**Recommended improvements** would be reducing system swappiness to optimise memory usage and allocating addictional CPU resourcses to support CPU intense workloads better.











