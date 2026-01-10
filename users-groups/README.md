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
