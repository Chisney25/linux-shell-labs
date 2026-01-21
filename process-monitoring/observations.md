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

