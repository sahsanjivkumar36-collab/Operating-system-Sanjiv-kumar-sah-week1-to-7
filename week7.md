Week 7 — Security Audit & System Evaluation

Home | Week 6 | Week 7

Overview

Week 7 focuses on conducting a comprehensive security audit and evaluating the overall system configuration. Using industry-standard security assessment tools and manual verification techniques, the Linux server was assessed for vulnerabilities, misconfigurations, and remaining risks.

This phase validates the effectiveness of all security controls implemented throughout the coursework and provides a critical evaluation of the system’s security posture and operational trade-offs.

Objectives

Perform a full operating system security audit

Identify vulnerabilities and configuration weaknesses

Remediate identified issues where possible

Evaluate system security, performance, and usability trade-offs

Assess residual risks and limitations

Deliverables

Security audit report

Lynis scan results (before and after remediation)

Network security assessment results

SSH security verification

Service inventory with justification

Remaining risk assessment

1. Security Audit Methodology

Security auditing was conducted using a combination of automated tools and manual verification. All testing was performed within the isolated VirtualBox host-only network to ensure ethical and compliant security assessment.

The audit focused on:

System hardening and configuration

Network exposure and service availability

Access control enforcement

Patch and update management

2. System Hardening Assessment (Lynis)
2.1 Lynis Overview

Lynis is an open-source security auditing tool used to assess Linux system configurations, identify vulnerabilities, and provide hardening recommendations.

2.2 Initial Lynis Scan

An initial Lynis scan was performed to establish a baseline security score.

Observed issues included:

Missing hardening recommendations

Informational warnings related to system configuration

Opportunities to improve logging and permissions

Screenshot Filename:
week7-lynis-before.png

2.3 Remediation Actions

Based on Lynis recommendations, the following actions were taken:

Strengthened file and directory permissions

Ensured all security updates were applied

Verified firewall and access control settings

Reviewed enabled services and disabled unnecessary components

2.4 Post-Remediation Scan

A second Lynis scan was conducted to measure improvements.

Results

Increased Lynis security score

Reduced number of warnings and suggestions

Improved compliance with best practices

Screenshot Filename:
week7-lynis-after.png

3. Network Security Assessment (nmap)
3.1 nmap Overview

The nmap tool was used to assess network exposure by identifying open ports and active services.

3.2 Scan Results

The network scan confirmed:

Only the SSH port was accessible

No unnecessary services were exposed

Firewall rules were enforced correctly

Screenshot Filename:
week7-nmap-scan.png

This result confirms effective network isolation and firewall configuration.

4. SSH Security Verification

SSH configuration was manually reviewed to verify compliance with security requirements.

Verified Controls

Password authentication disabled

Key-based authentication enforced

Root login disabled

Access restricted to a trusted IP

Screenshot Filename:
week7-ssh-verification.png

5. Service Inventory and Justification

A review of running services was conducted to ensure only required services were enabled.

Service Inventory
Service	Purpose	Justification
sshd	Remote administration	Required for secure management
fail2ban	Intrusion prevention	Protects against brute-force attacks
systemd-timesyncd	Time synchronisation	Required for accurate logging

All other non-essential services were disabled or removed to minimise attack surface.

6. Access Control Verification

Mandatory access control enforcement was verified using AppArmor.

Verification Steps

Confirmed AppArmor running in enforcing mode

Reviewed active profiles

Checked logs for denied operations

Screenshot Filename:
week7-apparmor-verification.png

7. Remaining Risk Assessment

Despite extensive hardening, some residual risks remain:

Zero-day vulnerabilities in system packages

Insider threats through authorised access

Resource exhaustion under extreme workloads

These risks are mitigated through monitoring, updates, and controlled access but cannot be fully eliminated.

8. Overall System Evaluation
Security Evaluation

Strong defence-in-depth implemented

Minimal exposed services

Effective intrusion detection and prevention

Performance Considerations

Security controls introduced minimal overhead

System remained responsive under load

Optimisation reduced unnecessary background activity

Trade-Off Analysis

Increased security slightly reduced administrative convenience

Monitoring introduced minimal resource overhead

Improved resilience outweighed performance costs

Reflection
Key Outcomes

Successfully applied industry-standard security auditing techniques

Identified and remediated configuration weaknesses

Achieved a strong overall security posture

Learning Objectives Achieved

Ability to conduct professional security audits

Critical evaluation of operating system security trade-offs

Understanding of risk management in system administration

References

Lynis Documentation
https://cisofy.com/lynis/

nmap Documentation
https://nmap.org/book/man.html

Ubuntu Security Guide
https://ubuntu.com/security
