# Linux Security Testing and Vulnerability Assessment

## Project Overview

This project is a beginner-friendly Linux security testing and vulnerability assessment lab built on Ubuntu Linux.

The project uses a Bash script to perform basic security checks on a Linux system. The script collects system information, identifies open network ports, checks firewall configuration, reviews SSH security settings, checks recent failed login attempts, verifies Fail2Ban status, lists running services, and searches selected system directories for world-writable files.

The purpose of the project is to practice Linux security administration, Bash scripting, system monitoring, and basic vulnerability assessment in a controlled lab environment.

## Objectives

* Practice Linux security administration using Ubuntu.
* Develop a Bash script for basic security assessment.
* Identify listening network ports and services.
* Check firewall configuration and status.
* Review SSH security configuration.
* Check recent failed SSH login attempts.
* Verify the status of Fail2Ban.
* Identify running system services.
* Check selected system directories for world-writable files.
* Document and interpret security assessment results.

## Environment

* **Operating System:** Ubuntu 24.04.3 LTS
* **Kernel:** 6.14.0-33-generic
* **Shell:** Bash
* **Environment:** Linux virtual machine
* **User:** basheer

## Tools and Technologies

* Ubuntu Linux
* Bash
* UFW (Uncomplicated Firewall)
* OpenSSH
* Fail2Ban
* Nginx
* systemd
* Git
* GitHub
* Linux command-line utilities

## Project Files

| File                  | Description                                         |
| --------------------- | --------------------------------------------------- |
| `security-testing`    | Bash script that performs the security checks       |
| `security-report.txt` | Saved output generated from the security assessment |

## Security Checks Performed

### 1. System Information

The script collects:

* Hostname
* Operating system information
* Linux kernel version

### 2. Open Network Ports

The script uses `ss` to identify listening network ports and services.

The assessment identified services listening on ports including:

* **22** — SSH
* **80** — HTTP
* **443** — HTTPS
* **631** — CUPS, locally bound

### 3. Firewall Status

The script checks the status of UFW.

The assessment showed that the firewall was active with rules allowing:

* OpenSSH
* Nginx Full

### 4. SSH Security Check

The script checks the SSH configuration file for:

* Root login configuration
* Password authentication configuration

The assessment showed that these settings were not explicitly configured in the main SSH configuration file.

### 5. Failed Login Attempts

The script reviews recent SSH logs for failed login attempts.

No recent failed SSH login attempts were displayed during the assessment.

### 6. Fail2Ban

The script checks whether Fail2Ban is installed and running.

The assessment confirmed that Fail2Ban was active with an `sshd` jail.

### 7. Running Network Services

The script lists currently running services using systemd.

Examples identified during the assessment include:

* Nginx
* Fail2Ban
* OpenSSH-related services
* NetworkManager
* system logging services

### 8. World-Writable File Check

The script searches `/etc` and `/usr/local/bin` for files with world-writable permissions.

No matching files were displayed during the assessment.

## How to Run the Project

### 1. Clone the repository

```bash
git clone git@github.com:Bashjsyk/linux-security-testing.git
```

### 2. Enter the project directory

```bash
cd linux-security-testing
```

### 3. Make the script executable

```bash
chmod +x security-testing
```

### 4. Run the security assessment

```bash
sudo bash ./security-testing
```

The script will display the security assessment results directly in the terminal.

## Save the Assessment Results

To display the results and save them to a report file at the same time:

```bash
sudo bash ./security-testing | tee security-report.txt
```

The results will be displayed in the terminal and saved to:

```text
security-report.txt
```

## Example Assessment Output

The script produces sections similar to:

```text
[1] SYSTEM INFORMATION
[2] OPEN NETWORK PORTS
[3] FIREWALL STATUS
[4] SSH SECURITY CHECK
[5] FAILED LOGIN ATTEMPTS
[6] FAIL2BAN STATUS
[7] RUNNING NETWORK SERVICES
[8] WORLD-WRITABLE FILE CHECK
```

The assessment ends with:

```text
Security testing completed.
Review the results above and document any findings.
```

## Security Findings

Based on the assessment performed in the lab:

* UFW firewall was active.
* SSH was listening on port 22.
* HTTP and HTTPS were provided by Nginx on ports 80 and 443.
* Fail2Ban was active with an SSH jail.
* No recent failed SSH login attempts were displayed.
* No world-writable files were found in the checked directories.
* Nginx was running as an active service.

These results represent the state of the specific Ubuntu lab environment at the time of testing.

## Limitations

This project is a **basic security assessment tool** and is not a replacement for professional vulnerability scanners or a complete security audit.

The script:

* Performs local checks only.
* Does not exploit vulnerabilities.
* Does not perform penetration testing.
* Does not guarantee that the system is completely secure.
* Checks only the directories and configurations specifically included in the script.

Additional security tools and manual analysis would be required for a comprehensive security assessment.

## Learning Outcomes

Through this project, I practiced:

* Linux command-line administration
* Bash scripting
* File permissions
* Network port identification
* Firewall management
* SSH security
* Log analysis
* Fail2Ban monitoring
* System service management
* Basic security assessment
* Git and GitHub project management

## Disclaimer

This project was created for educational and defensive cybersecurity training purposes in a controlled Linux environment.

The script is intended for systems that I own or have permission to assess. It does not contain credential-stealing functionality or destructive exploitation techniques.

## Author

**Basheer Ogungbayi**

Computer Science Student
Cybersecurity Enthusiast
