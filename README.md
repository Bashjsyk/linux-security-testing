# Linux Security Testing and Vulnerability Assessment Using Ubuntu Linux

## Project Overview

This project demonstrates basic security testing and vulnerability assessment using Ubuntu Linux.

The project was created to gain practical experience with Linux security administration, Bash scripting, network security, firewall configuration, SSH security, log analysis, intrusion prevention, system services, and basic security monitoring.

## Project Objectives

The main objectives of this project are to:

* Perform basic security checks on an Ubuntu Linux system.
* Collect system and operating system information.
* Identify open and listening network ports.
* Check the status of the UFW firewall.
* Review SSH security configuration.
* Check recent failed SSH login attempts.
* Check the status of Fail2Ban.
* Identify running system services.
* Check for world-writable files in selected system directories.
* Generate and save a security assessment report.
* Document the project and manage it using GitHub.

## Technologies and Tools

* Ubuntu Linux
* Bash Scripting
* OpenSSH
* UFW (Uncomplicated Firewall)
* Fail2Ban
* Nginx
* systemd
* Git
* GitHub
* VirtualBox

## Security Checks

### System Information

The script collects important system information, including:

* Hostname
* Operating system
* Linux kernel version

### Network Ports

The script uses `ss` to identify open and listening network ports.

The assessment identified services using:

* SSH: Port 22
* HTTP: Port 80
* HTTPS: Port 443
* CUPS: Port 631 (locally bound)

### UFW Firewall

The UFW firewall was checked to verify its current status and configured rules.

The assessment confirmed that the firewall was active and allowed the required SSH and Nginx services.

### SSH Security

The script checks the SSH configuration for:

* Root login configuration
* Password authentication configuration

This helps identify important SSH security settings that may require further review.

### Failed Login Attempts

Recent SSH logs were checked for failed authentication attempts.

No recent failed SSH login attempts were displayed during the assessment.

### Fail2Ban

Fail2Ban was checked to verify that the intrusion prevention service was active.

The assessment confirmed that Fail2Ban was running with an `sshd` jail.

### Running Services

The script checks currently running system services using `systemctl`.

Services identified during the assessment included:

* Nginx
* Fail2Ban
* NetworkManager
* CUPS
* System logging services

### World-Writable Files

The script searches selected system directories for files with world-writable permissions.

The checked directories were:

```text
/etc
/usr/local/bin
```

No matching world-writable files were displayed during the assessment.

## Security Assessment Report

The results of the security assessment can be saved to a report file using:

```bash
sudo bash ./security-testing | tee security-report.txt
```

The report contains the results of the security checks performed by the script.

## Testing and Verification

The following security checks were successfully performed:

* System information
* Network ports
* UFW firewall
* SSH configuration
* Failed SSH login attempts
* Fail2Ban status
* Running system services
* World-writable file check
* Security assessment report generation

## Project Files

```text
linux-security-testing/
├── security-testing
├── security-report.txt
└── README.md
```

## How to Run

1. Start the Ubuntu Virtual Machine in VirtualBox.
2. Open the terminal.
3. Navigate to the project directory:

```bash
cd ~/linux-security-testing
```

4. Make the script executable:

```bash
chmod +x security-testing
```

5. Run the security testing script:

```bash
sudo bash ./security-testing
```

6. To display the results and save them to a report:

```bash
sudo bash ./security-testing | tee security-report.txt
```

7. Check the firewall:

```bash
sudo ufw status
```

8. Check Fail2Ban:

```bash
sudo fail2ban-client status
```

9. Check running network services:

```bash
sudo systemctl --type=service --state=running
```

## Learning Outcomes

This project provided practical experience with:

* Linux security administration
* Bash scripting
* Network port analysis
* Firewall configuration
* SSH security
* Log analysis
* Fail2Ban
* Linux system services
* File permissions
* Basic vulnerability assessment
* Security reporting
* Git and GitHub
