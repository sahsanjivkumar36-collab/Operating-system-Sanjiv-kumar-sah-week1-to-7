Week 5 — Advanced Security & Monitoring Infrastructure
Home | Week 4 | Week 5 | Week 6 →
________________________________________
Overview
Week 5 focuses on strengthening the security posture of the Linux server by implementing advanced security controls and developing monitoring capabilities. Building upon the foundational security configuration from Week 4, this phase introduces mandatory access control, automated security updates, intrusion detection, and custom automation scripts.
The goal of this week is to move beyond basic hardening and towards continuous security verification and performance monitoring, reflecting professional system administration practices.
________________________________________
Objectives
•	Implement mandatory access control using AppArmor
•	Configure automatic security updates
•	Deploy intrusion detection and prevention mechanisms
•	Develop a security baseline verification script
•	Create a remote monitoring script for performance data collection
________________________________________
Deliverables
•	AppArmor configuration and verification evidence
•	Automatic security updates configuration
•	fail2ban installation and configuration
•	Security baseline verification script (security-baseline.sh)
•	Remote monitoring script (monitor-server.sh)
________________________________________
1. Mandatory Access Control (AppArmor)
1.1 AppArmor Overview
AppArmor provides mandatory access control (MAC) by enforcing security profiles that restrict how applications can access system resources. Unlike traditional discretionary access control, AppArmor limits damage even if a service is compromised.
________________________________________
1.2 AppArmor Configuration
AppArmor was enabled and verified on the Ubuntu Server.
Actions Performed
•	Verified AppArmor service status
•	Confirmed active enforcement mode
•	Reviewed loaded security profiles
Screenshot Filename:
week5-apparmor-status.png
This ensures that critical services operate under defined security constraints.
________________________________________
1.3 AppArmor Monitoring
AppArmor logs are used to detect and investigate policy violations.
•	Log file location: /var/log/syslog
•	Monitored for denied operations and profile violations
Screenshot Filename:
week5-apparmor-logs.png
________________________________________
2. Automatic Security Updates
2.1 Configuration of Unattended Upgrades
Automatic security updates were configured to ensure timely patching of vulnerabilities.
Key Features Enabled
•	Daily security update checks
•	Automatic installation of critical patches
•	Logging of update activity
Screenshot Filename:
week5-unattended-upgrades.png
This reduces the risk of exploitation from known vulnerabilities.
________________________________________
2.2 Verification
Update logs were reviewed to confirm that unattended upgrades were functioning correctly.
Screenshot Filename:
week5-unattended-upgrades-log.png
________________________________________
3. Intrusion Detection with fail2ban
3.1 fail2ban Overview
fail2ban protects the system by monitoring log files for suspicious activity, such as repeated failed login attempts, and automatically blocking offending IP addresses.
________________________________________
3.2 Installation and Configuration
fail2ban was installed and configured to protect SSH access.
Configuration Highlights
•	Enabled SSH jail
•	Configured retry limits and ban duration
•	Integrated with UFW firewall rules
Screenshot Filename:
week5-fail2ban-status.png
________________________________________
3.3 Verification
The fail2ban service status and active jails were verified to ensure proper operation.
Screenshot Filename:
week5-fail2ban-jails.png
________________________________________
4. Security Baseline Verification Script
4.1 Script Purpose
The security-baseline.sh script was developed to automatically verify that all required security controls from Weeks 4 and 5 are correctly implemented.
________________________________________
4.2 Verified Controls
The script checks for:
•	SSH key-based authentication enforcement
•	Password authentication disabled
•	Firewall enabled with restricted SSH access
•	AppArmor enabled and enforcing
•	Automatic security updates enabled
•	fail2ban service running
________________________________________
4.3 Script Execution
The script is executed on the server via SSH and provides clear pass/fail output for each security control.
Screenshot Filename:
week5-security-baseline-script.png
All script logic is commented line-by-line to explain functionality and decision-making.
________________________________________
5. Remote Monitoring Script
5.1 Script Purpose
The monitor-server.sh script was developed to run on the workstation and collect performance metrics from the server via SSH.
________________________________________
5.2 Collected Metrics
The script collects:
•	CPU usage
•	Memory utilisation
•	Disk usage
•	Network statistics
•	System uptime and load averages
________________________________________
5.3 Monitoring Workflow
•	Script initiates SSH connection to the server
•	Executes read-only system commands
•	Stores output in structured files for later analysis
Screenshot Filename:
week5-monitoring-script.png
This approach ensures monitoring does not interfere with server performance.
________________________________________
6. Integration and Validation
Both scripts were tested to ensure:
•	Secure execution over SSH
•	No requirement for interactive input
•	Clear and readable output
•	Compatibility with later performance analysis
This automation supports consistent verification and monitoring throughout the remainder of the coursework.
________________________________________
Reflection
Key Security Enhancements
•	Enforced mandatory access control using AppArmor
•	Reduced vulnerability exposure through automatic updates
•	Added intrusion detection and response capabilities
•	Automated security verification and monitoring
Challenges Encountered
•	Interpreting AppArmor log entries
•	Ensuring scripts run non-interactively over SSH
•	Balancing security checks with system performance
Learning Objectives Achieved
•	Implementation of advanced operating system security controls
•	Development of automation scripts for security and monitoring
•	Understanding of defence-in-depth strategies
________________________________________
References
Ubuntu AppArmor Documentation
https://ubuntu.com/server/docs/security-apparmor
fail2ban Documentation
https://www.fail2ban.org/wiki/index.php/Main_Page
Unattended Upgrades Documentation
https://wiki.debian.org/UnattendedUpgrades


