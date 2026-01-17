# Linux Shell Labs

This repository documents practical Linux knowledge required for DevOps engineering.

## Scope
- Filesystem navigation
- Core Linux CLI operations

All changes are delivered via feature branches and reviewed through pull requests.

## top Observations

- Load average / CPU usage: 0.50, 0.60, 0.55 (1, 5, 15 min) / CPU 15% usage
- Memory usage: 6.2 GB used / 16 GB total
- Top CPU-consuming process: chrome.exe (12%)
- Top memory-consuming process: code.exe (VS Code) (1.8 GB)
- Notes on system health: System is healthy. CPU and memory usage are low to moderate. No processes are stuck or unresponsive.

## htop / Task Manager Observations

- Differences vs top: Shows interactive color bars, tree view for parent/child processes, easy filtering and sorting
- Useful features (tree view, filtering): Can view process hierarchy, sort by CPU or memory instantly, search for specific processes
- Observed high resource processes: chrome.exe (CPU 12%, Mem 1.8 GB), code.exe (CPU 5%, Mem 1.5 GB), explorer.exe (CPU 1%, Mem 250 MB)

## vmstat / Resource Monitor Observations

- Run queue length / CPU load: 1–2 processes waiting
- CPU: user 12%, system 3%, idle 85%, wait 0%
- Memory: free 9.8 GB, used 6.2 GB, buffers/cache 1.5 GB
- Swap / pagefile usage: 0 MB
- Disk I/O or blocking processes: No significant I/O wait, disk healthy, top I/O: chrome.exe and code.exe



