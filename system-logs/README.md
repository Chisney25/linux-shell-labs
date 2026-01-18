# Log Management & System Logs Lab

## Objective
Learn to inspect Linux system logs and analyze system behavior, authentication, and service-level events.

## Tools
- journalctl
- /var/log/syslog
- /var/log/auth.log
- grep for filtering

## Logging Architecture Overview

### systemd-journald
systemd-journald collects logs from the system and running services in one place.
- It stores logs from the kernel and system services.
- Logs can be viewed using the journalctl command.
- It helps engineers quickly check what happened on the system.

### Traditional Log Files (/var/log)
Some logs are written as files under /var/log.
- syslog contains general system and service messages.
- auth.log contains authentication-related events like sudo and SSH.
- These files are useful for auditing and troubleshooting.

### Relationship Between journald and syslog
On many systems, logs collected by journald are also written to files in /var/log.
- journald acts as the main log collector.
- syslog provides file-based logs for persistence.
- Engineers may check both when analysing issues.

