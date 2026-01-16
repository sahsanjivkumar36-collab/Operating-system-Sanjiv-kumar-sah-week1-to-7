Week 4 — Initial System Configuration & Security Implementation
Home | Week 3 | Week 4 | Week 5 →
________________________________________
Overview
Week 4 focuses on deploying the Linux server and implementing foundational security controls. All configuration tasks are performed remotely via SSH from the workstation, enforcing professional remote administration practices and command-line proficiency.
This phase establishes a secure baseline by hardening SSH access, configuring a firewall, and implementing user and privilege management. These controls significantly reduce the server attack surface and prepare the system for advanced security and monitoring in later phases.
________________________________________
Objectives
•	Configure secure SSH access using key-based authentication
•	Disable insecure authentication mechanisms
•	Implement host-based firewall rules
•	Create and manage non-root administrative users
•	Demonstrate secure remote administration via SSH
________________________________________
Deliverables
•	SSH key-based authentication configuration
•	Firewall rules permitting SSH access from a single workstation
•	User and privilege management implementation
•	Configuration file comparisons (before and after)
•	Evidence of remote administration via SSH
________________________________________
1. Secure SSH Configuration
1.1 SSH Key-Based Authentication
Key-based authentication was configured to replace password-based login, providing stronger security against brute-force attacks.
Steps Performed
•	Generated an SSH key pair on the workstation
•	Copied the public key to the server using secure methods
•	Verified key-based login functionality
Screenshot Filename:
week4-ssh-keygen.png
Screenshot Filename:
week4-ssh-key-login.png
________________________________________
1.2 SSH Hardening
The SSH daemon configuration was modified to enforce secure access policies.
Key Configuration Changes
•	Password authentication disabled
•	Root login over SSH disabled
•	SSH access restricted to authorised users
Configuration File:
/etc/ssh/sshd_config
Screenshot Filename (Before):
week4-sshd-config-before.png
Screenshot Filename (After):
week4-sshd-config-after.png
These changes ensure that only trusted users with valid SSH keys can access the server.
________________________________________
2. Firewall Configuration
2.1 Firewall Setup
A host-based firewall was configured to control inbound network traffic.
•	Firewall tool: UFW (Uncomplicated Firewall)
•	Default policy: Deny all incoming connections
•	Allowed service: SSH
Screenshot Filename:
week4-ufw-enable.png
________________________________________
2.2 Restricting SSH Access
SSH access was restricted to the workstation’s IP address to further reduce exposure.
Firewall Rules Implemented
•	Allow SSH from workstation IP only
•	Deny all other inbound traffic
Screenshot Filename:
week4-ufw-rules.png
These rules enforce the principle of least privilege at the network level.
________________________________________
3. User and Privilege Management
3.1 Non-Root Administrative User
A non-root administrative user was created to perform system management tasks securely.
User Management Actions
•	Created a new user account
•	Assigned sudo privileges
•	Disabled direct root login
Screenshot Filename:
week4-useradd.png
Screenshot Filename:
week4-sudo-check.png
Using a non-root user reduces the risk of accidental system damage and limits the impact of potential compromise.
________________________________________
4. Remote Administration Evidence
All system configuration tasks were performed remotely from the workstation via SSH.
Evidence Includes
•	Successful SSH login using key-based authentication
•	Execution of administrative commands via SSH
•	No direct console access used for routine administration
Screenshot Filename:
week4-remote-ssh-session.png
This confirms compliance with the coursework administrative constraint.
________________________________________
5. Firewall Ruleset Documentation
The complete firewall ruleset was documented to provide transparency and auditability.
Documented Information
•	Default inbound and outbound policies
•	Allowed services and ports
•	IP-based access restrictions
Screenshot Filename:
week4-ufw-status-verbose.png
________________________________________
Reflection
Key Security Improvements
•	Eliminated password-based SSH authentication
•	Restricted network access to a trusted workstation
•	Enforced least-privilege user management
Challenges Encountered
•	Avoiding accidental lockout during SSH hardening
•	Ensuring firewall rules were applied in the correct order
•	Verifying changes remotely without console access
Learning Objectives Achieved
•	Secure remote system administration using SSH
•	Practical firewall configuration and network restriction
•	Application of least-privilege and defence-in-depth principles
________________________________________
References
OpenSSH Manual
https://man.openbsd.org/sshd
Ubuntu UFW Documentation
https://help.ubuntu.com/community/UFW


