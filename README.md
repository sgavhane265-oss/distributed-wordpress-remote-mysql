# Distributed WordPress Deployment with Remote MariaDB

A practical Linux and web-infrastructure internship project implemented using **two Oracle VirtualBox virtual machines**.

## Project Overview

The project demonstrates a two-tier WordPress deployment:

- **Ubuntu VM**: Web/application server
  - Apache2
  - PHP
  - WordPress
- **OpenSUSE VM**: Database server
  - MariaDB
- **Network communication**: TCP port `3306`

The WordPress application running on Ubuntu connects to the MariaDB database running remotely on OpenSUSE.

## Architecture

```text
                    Oracle VirtualBox
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
       Ubuntu VM                  OpenSUSE VM
      172.22.62.219              172.22.62.225
              │                         │
              │                         │
       Apache + PHP                MariaDB
         WordPress                    │
              │                       │
              └────── TCP 3306 ───────┘
```

## Environment

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Web Server | Ubuntu |
| Web Server IP | `172.22.62.219` |
| Database Server | OpenSUSE |
| Database Server IP | `172.22.62.225` |
| Web Server | Apache2 |
| Application | WordPress |
| Database | MariaDB |
| Database Name | `wordpress` |
| Database User | `wpuser` |
| Database Port | `3306` |

## Work Performed

The practical implementation included:

1. Identifying the IP addresses of both virtual machines.
2. Testing connectivity between Ubuntu and OpenSUSE.
3. Installing MariaDB on OpenSUSE.
4. Creating the `wordpress` database.
5. Creating the dedicated `wpuser` remote database account.
6. Granting database privileges.
7. Configuring MariaDB for network access.
8. Restarting and verifying the MariaDB service.
9. Verifying TCP port `3306`.
10. Configuring `firewalld` to allow MySQL/MariaDB traffic.
11. Testing remote MariaDB connectivity from Ubuntu.
12. Installing the MySQL client on Ubuntu.
13. Installing Apache2.
14. Installing PHP and required PHP extensions.
15. Verifying PHP through Apache.
16. Downloading and extracting WordPress.
17. Deploying WordPress into the Apache web root.
18. Configuring WordPress to use the remote MariaDB server.
19. Completing the WordPress installation.
20. Verifying the WordPress dashboard and public site.
21. Verifying WordPress tables in MariaDB.
22. Verifying WordPress post data in `wp_posts`.

## Documentation

The complete internship report contains the implementation steps and the screenshots captured during the practical.

**[Open the complete internship documentation](documentation/Distributed-WordPress-Remote-MySQL-Final-Internship-Documentation.docx)**

## Evidence

The `screenshots/` directory contains the complete evidence set:

```text
step-01.png
step-02.png
...
step-54.png
```

Each screenshot corresponds to an implementation step in the documentation.

## Important Note About the Virtual Machines

The project was performed inside Oracle VirtualBox virtual machines.

The actual VM disk images, snapshots, ISO files, and VirtualBox configuration files are **not included** in this repository because they are large machine-specific artifacts. The repository instead contains the documentation and implementation evidence needed to understand and review the project.

## Security

Sensitive credentials should never be committed to GitHub.

This repository intentionally excludes:

```text
wp-config.php
.env
SSH private keys
VirtualBox disk images
VirtualBox snapshots
ISO files
```

The database password visible in one supplied terminal screenshot has been redacted in the published evidence.

The MariaDB `bind-address = 0.0.0.0` configuration was used for this controlled lab environment. Production deployments should restrict database access to trusted hosts/networks.

## Technologies

- Linux
- Ubuntu
- OpenSUSE
- MariaDB
- Apache2
- PHP
- WordPress
- Oracle VirtualBox
- firewalld
- systemd
- TCP/IP networking

## Skills Demonstrated

- Linux system administration
- Virtual machine administration
- Network troubleshooting
- Remote database configuration
- MariaDB administration
- Firewall configuration
- Apache web server deployment
- PHP configuration
- WordPress deployment
- Application/database integration
- Technical documentation
- Git/GitHub project organization

## Project Result

The final environment successfully demonstrated WordPress running on Ubuntu while using a remote MariaDB database hosted on OpenSUSE.

This provides practical experience with a basic distributed application architecture and the Linux administration tasks required to deploy and connect its components.
