# Linux Permissions & Ownership

Linux permissions control who can read, write, or execute files and directories.

Misconfigured permissions are a common root cause of deployment failures, security incidents, and broken CI/CD pipelines.

---

## Permission Model Overview

Each file or directory has:

- **Owner (u)** – usually the creator
- **Group (g)** – a collection of users
- **Others (o)** – everyone else

Each category can have:

- **Read (r)** – view contents
- **Write (w)** – modify contents
- **Execute (x)** – run file or access directory

---

## Viewing Permissions

```bash
ls -l
```

Example output:

```bash
-rwxr-xr-- 1 devuser devops 4096 script.sh
```

Breakdown:

- `-` → file type (`d` = directory)
- `rwx` → owner permissions
- `r-x` → group permissions
- `r--` → others permissions

---

## chmod — Change Permissions

### Symbolic mode

```bash
chmod u+x script.sh
chmod g-w config.yaml
chmod o-r secret.txt
```

### Numeric (octal) mode

- `r = 4`
- `w = 2`
- `x = 1`

Examples:

```bash
chmod 755 script.sh
chmod 644 config.yaml
```

DevOps relevance:

- Executable scripts in pipelines → `755`
- Config files → `600` or `640`

---

## chown — Change Ownership

```bash
chown user file
chown user:group file
```

Example:

```bash
chown appuser:appgroup app.log
```

Used when:

- Containers write to mounted volumes
- Services run as non-root users

---

## chgrp — Change Group Ownership

```bash
chgrp devops shared_dir
```

Common in team environments where multiple users need access without root.

---

## Directory Permissions (Critical Concept)

- **Read (r)** → list directory contents
- **Write (w)** → create/delete files
- **Execute (x)** → access directory

Example:

```bash
chmod 750 /var/app
```

Allows owner full access, group read/execute, blocks others entirely.

---

## Practical DevOps Scenarios

- CI job fails → script lacks execute permission
- Application crashes → log directory not writable
- Container exits → volume owned by root
- Security issue → secrets readable by others

Permissions are not theory — they directly affect production stability.
