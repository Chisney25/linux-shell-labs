## Background Processes

Linux allows processes to run in the background, freeing the terminal for other tasks. This is common in automation, long-running jobs, and operational scripts.

### Running a Process in the Background

Appending `&` runs a command in the background.

```bash
sleep 300 &
```
This returns control to the terminal while the process continues running.

---

### Job Control

The shell provides job control commands to manage background processes.

```bash
jobs
```
Lists active background jobs in the current shell.
```bash
fg %1
``` 
Brings job 1 to the foreground.
```bash
bg %1
```
Resumes a stopped job in the background.

---

## Signals and Process Termination

Linux uses signals to communicate with running processes.

```bash
kill <PID>
```
Sends the default SIGTERM signal, requesting graceful termination.

```bash
kill -9 <PID>
```
Sends SIGKILL, forcing immediate termination. This should be a last resort.

---

DevOps Relevance
- Stop stuck or runaway processes 
- Control long-running jobs in CI/CD pipelines
- Perform safe shutdowns during maintenance
- Diagnose and recover from production incidents

Signals are operational tools, not theory. Misuse can cause downtime.

---
