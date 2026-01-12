# Linux Networking & Ports

Networking is a core DevOps skill. Understanding ports, services, and connections allows engineers to troubleshoot deployments, debug CI/CD pipelines, and ensure application availability.

---

## Networking Fundamentals

- A **host** has an IP address that identifies it on a network.
- **Ports** are endpoints for services and applications.
- **TCP** and **UDP** are the primary protocols for communication.
- Services listen on ports to accept connections from clients.

DevOps relevance:
- Troubleshoot service failures
- Validate firewall and security group rules
- Monitor and debug application connectivity

---

## Viewing Open Ports and Connections

Linux provides tools to inspect active connections and listening ports.

### Using `ss`

```bash
ss -tuln
```
- -t → TCP connections
- -u → UDP connections
- -l → listening sockets
- -n → show numeric addresses/ports

Using netstat (older tool)
```bash
netstat -tuln
```
- Lists listening ports and active connections
- Useful for troubleshooting service reachability

DevOps relevance:
- Confirm services are listening on expected ports
- Validate firewall rules
- Debug connectivity issues in production

---

## Firewall Basics and Port Testing

Linux uses firewalls to control network traffic. Common tools include **ufw**, **iptables**, and **firewalld**.

### Check firewall status with ufw

```bash
sudo ufw status
```
Allow a port
```bash
sudo ufw allow 8080/tcp
```
Deny a port
```bash
sudo ufw deny 22/tcp
```
Test connectivity with nc (netcat)
```bash
nc -zv 127.0.0.1 8080
```
- -z → scan without sending data
- -v → verbose output

DevOps relevance:
- Validate network connectivity for applications
- Ensure services are reachable in CI/CD pipelines
- Secure production hosts by controlling port access

---

## Common Ports in DevOps

| Service          | Default Port |
|-----------------|-------------|
| HTTP             | 80          |
| HTTPS            | 443         |
| SSH              | 22          |
| MySQL            | 3306        |
| PostgreSQL       | 5432        |
| Redis            | 6379        |

DevOps relevance:
- Quickly identify which ports services should listen on
- Troubleshoot connectivity issues in staging/production
- Ensure CI/CD pipelines can access required services
- Aid in writing monitoring and alerting rules

---