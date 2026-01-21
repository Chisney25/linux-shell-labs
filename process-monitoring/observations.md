## Process Discovery (ps)

- The system is running multiple background services and user processes.
- Top CPU-consuming processes include [/usr/bin/containerd, /usr/bin/python3/home/devcontainers], which is expected.
- Top memory-consuming processes include [/usr/bin/dockerd -H fd://, /usr/bin/containerd].
- No single process appears to be consuming excessive CPU or memory.

## System-Wide Resource Analysis (vmstat)

- CPU: [0]% user, [0]% system, [99]% idle, [0]% IO wait
- Memory: [1416440] KB free, [195472] KB cached
- Swap: [0] KB in, [0] KB out
- Process queue: [1] running, [0] blocked

**Interpretation**:
- Low `running process queue` + high `idle CPU` → system is idle
- High `wait %` → IO bottleneck
- Memory or swap pressure → potential memory-bound state

## Memory & Load Analysis

### Memory (free -h)
- Total memory:1.9Gi
- Available memory:1.5Gi
- Swap usage:0B
- Interpretation:the available memory compared to the total memory shows that there is still enough memory

### Load (uptime)
- Load averages (1m;0.00, 5m;0.01, 15m;0.00):
- CPU cores:2
- Interpretation:since Load << cores → system is healthy

