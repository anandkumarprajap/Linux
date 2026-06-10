# Linux Package Management and Nginx Service

## Screenshot 1

![APT Update and Upgrade](7.png)

## Screenshot 2

![Installing Packages](8.png)

## Screenshot 3

![Nginx Status Running](9.png)

## Screenshot 4

![Stopping Nginx](10.png)

## Screenshot 5

![Nginx Inactive](11.png)

## Screenshot 6

![Starting Nginx Again](12.png)

## Screenshot 7

![Starting Nginx Again](13.png)
---

# 1. Update Package Repository

Command:

```bash
sudo apt-get update
```

### Purpose

Downloads the latest package information from Ubuntu repositories.

Example Output:

```text
Hit:1 ubuntu repository
Get:2 ubuntu-updates
Fetched 137 kB
Reading package lists... Done
```

### Important

* Updates package information only.
* Does not install or upgrade software.

---

# 2. Upgrade Installed Packages

Command:

```bash
sudo apt-get upgrade
```

### Purpose

Upgrades installed packages to newer versions.

Example:

```text
4 upgraded, 0 newly installed
Need to get 41.9 MB
Do you want to continue? [Y/n]
```

### Difference

```bash
sudo apt-get update
```

Updates package list.

```bash
sudo apt-get upgrade
```

Installs available updates.

---

# 3. Install Docker

Command:

```bash
sudo apt-get install docker.io
```

### Purpose

Installs Docker Engine from Ubuntu repositories.

Docker is used to create and manage containers.

---

# 4. Install Nginx

Command:

```bash
sudo apt-get install nginx
```

### Purpose

Installs the Nginx web server.

Output:

```text
nginx is already the newest version
```

Meaning Nginx was already installed.

---

# 5. Check Nginx Service Status

Command:

```bash
systemctl status nginx
```

Output:

```text
Active: active (running)
```

### Meaning

Nginx is currently running and serving web requests.

Important fields:

| Field    | Meaning                      |
| -------- | ---------------------------- |
| Loaded   | Service configuration loaded |
| Active   | Current service state        |
| Main PID | Process ID                   |
| Memory   | RAM usage                    |
| Tasks    | Running threads/processes    |

---

# 6. Stop Nginx Service

Command:

```bash
sudo systemctl stop nginx
```

### Purpose

Stops the Nginx service.

Verify:

```bash
systemctl status nginx
```

Output:

```text
Active: inactive (dead)
```

Meaning:

Nginx is no longer running.

---

# 7. Check Service Using Service Command

Command:

```bash
service nginx status
```

### Purpose

Alternative method to view service status.

Output:

```text
Active: inactive (dead)
```

Shows the same information as systemctl.

---

# 8. Stop Nginx Using Service Command

Command:

```bash
sudo service nginx stop
```

### Purpose

Stops Nginx using the legacy service command.

---

# 9. Start Nginx Using Service Command

Command:

```bash
sudo service nginx start
```

### Purpose

Starts the Nginx service.

Verify:

```bash
systemctl status nginx
```

Output:

```text
Active: active (running)
```

---

# 10. Service Lifecycle

```text
Install Nginx
      │
      ▼
sudo apt-get install nginx
      │
      ▼
Check Status
      │
      ▼
systemctl status nginx
      │
      ▼
Stop Service
      │
      ▼
sudo systemctl stop nginx
      │
      ▼
Status = inactive (dead)
      │
      ▼
Start Service
      │
      ▼
sudo service nginx start
      │
      ▼
Status = active (running)
```

---

# Difference Between systemctl and service

## systemctl

Modern service manager.

Examples:

```bash
systemctl status nginx
systemctl start nginx
systemctl stop nginx
systemctl restart nginx
```

---

## service

Older but simpler interface.

Examples:

```bash
service nginx status
service nginx start
service nginx stop
```

---

# Useful Commands Summary

```bash
sudo apt-get update

sudo apt-get upgrade

sudo apt-get install docker.io

sudo apt-get install nginx

systemctl status nginx

sudo systemctl stop nginx

service nginx status

sudo service nginx stop

sudo service nginx start
```

---

# Key Learning

* `apt-get update` refreshes package information.
* `apt-get upgrade` upgrades installed packages.
* `apt-get install` installs software packages.
* Docker is installed using `docker.io`.
* Nginx is a web server and reverse proxy.
* `systemctl status` checks service health.
* `systemctl stop` stops a service.
* `service start` starts a service.
* `active (running)` means the service is working.
* `inactive (dead)` means the service is stopped.
