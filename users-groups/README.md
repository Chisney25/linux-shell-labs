# Linux Users, Groups, and Sudo

Understanding users, groups, and sudo is critical for secure system operations, CI/CD agents, and containerized workloads.

---

## User and Group Basics

- **Users**: Individual accounts with a UID, home directory, and shell.
- **Groups**: Collections of users for shared permissions.
- **/etc/passwd**: Stores user account information.
- **/etc/group**: Stores group definitions.

---

## Adding Users and Groups

### Add a new user
```bash
sudo useradd alice
sudo passwd alice
```

### Add a new group
```bash
sudo groupadd devops
```

### Add a user to a group
```bash
sudo usermod -aG devops alice
```

---

## Sudo Essentials

- `sudo` allows a permitted user to execute commands as root.
- Configuration in `/etc/sudoers` (always edit with `visudo`).
- Avoid running services as root; use sudo sparingly.

### Example
```bash
sudo systemctl restart nginx
```

---

## Practical DevOps Scenarios

- CI/CD pipelines fail → user does not have sudo permissions.
- Containers crash → mounted volume not writable by service user.
- Security incident → root access too permissive.

---

## Notes

All examples are safe to test locally in your WSL environment.  
Changes will be committed via feature branches and merged to main through PRs.

---

### Exercise 1 — Inspect Users & Groups

- `/etc/passwd` lists all users and basic info
- `/etc/group` lists groups and members
- `whoami` shows current user
- `groups` shows current user’s group memberships

> DevOps relevance: Understanding existing users/groups is critical before granting permissions, adding sudo access, or configuring CI/CD pipelines.

---

### Exercise 2 — Create Users & Groups

- `groupadd devops` creates a group
- `useradd -m -G devops alice` creates a user with a home directory and adds to a group
- `passwd` sets the user password
- `id alice` and `groups alice` verify creation

> DevOps relevance: CI/CD agents, container users, and deployment scripts rely on correct user/group setup.

---

### Exercise 3 — Test Sudo Permissions

- `sudo` allows a permitted user to execute commands as root
- Misconfigured sudo can break CI/CD pipelines or cause security incidents
- Always edit `/etc/sudoers` via `visudo` if changes are needed

> DevOps relevance: Ensuring least privilege and controlled root access prevents accidental system-wide changes.

---