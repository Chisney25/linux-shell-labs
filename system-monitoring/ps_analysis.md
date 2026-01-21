## CPU Usage per Process
- Command used:
  ps -eo pid,comm,%cpu,%mem --sort=-%cpu | head -n 10
- Observations:
  - The highest CPU usage was observed from the containerd and python3 process respectively with a 0.1% CPU usage each, indicating containerd and python workloads were actively running. CPU consumption was concentrated in a small number of processes rather than evenly distributed.

## Memory Usage per Process
- Command used:
  ps -eo pid,comm,%cpu,%mem --sort=-%mem | head -n 10
- Observations:
  - Memory usage was dominated by long-running services such as dockerd(4.1%) and containerd(2.3%), while CPU-intensive processes did not necessarily consume significant memory.

## RSS Memory Analysis
- Command used:
  ps -eo pid,comm,rss --sort=-rss | head -n 10
- Observations:
  - Processes with high RSS values were not always the same processes consuming high CPU, showing that memory pressure and CPU load are often caused by different workloads.

