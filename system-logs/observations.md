## Boot Log Analysis

- Observed several informational messages from system services during startup.
- Noted [12] warning-level messages related to [WSL Connection Error].
- Some error messages were present (majority of them were about gettiing address information for WSL connection, which kept on failing at intervals).
- Overall system boot appeared healthy.

## Service-Level Log Analysis

### nginx.service
- Service status: active and running.
- Logs show normal startup and request handling activity.
- No repeated restarts or critical errors observed.

### rsyslog.service
- Service status: active and running.
- Logs indicate successful log processing and forwarding.
- No failures or disruptions detected in the logging pipeline.

## Authentication & Security Log Analysis

- Authentication logs record user login activity and privilege escalation.
- Observed multiple sudo-related entries indicating administrative actions.
- SSH-related events show successful sessions with no failed login attempts observed.
- No suspicious or repeated authentication failures detected.

