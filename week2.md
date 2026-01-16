Week 2 — Security Planning & Testing Methodology
Home | Week 1 | Week 2 | Week 3 →
________________________________________
Overview
Week 2 focuses on designing a comprehensive security baseline and defining a structured performance testing methodology for the Linux server environment. Rather than implementing security controls at this stage, the emphasis is on planning, threat identification, and justification of security and monitoring decisions before deployment.
This phase ensures that security hardening and performance evaluation in later weeks are systematic, measurable, and aligned with industry best practices.
________________________________________
Objectives
•	Design a security baseline for the Linux server
•	Define a structured performance testing methodology
•	Identify potential operating system security threats
•	Map threats to appropriate mitigation strategies
•	Prepare for secure and measurable system evaluation
________________________________________
Deliverables
•	Performance testing and monitoring plan
•	Security configuration checklist
•	Threat model with identified risks and mitigations
________________________________________
1. Performance Testing Methodology
1.1 Testing Approach
Performance testing will be conducted remotely from the workstation using SSH-based monitoring tools. This ensures that all measurements reflect realistic remote administration scenarios and avoids introducing unnecessary load through local server-side interfaces.
The methodology is designed to measure operating system behaviour under different workloads while maintaining consistency and reproducibility.
________________________________________
1.2 Metrics to be Collected
The following metrics will be monitored throughout baseline and load testing:
•	CPU utilisation
•	Memory usage
•	Disk I/O activity
•	Network throughput and latency
•	System load averages
•	Service response times (where applicable)
________________________________________
1.3 Monitoring Methodology
Monitoring will be performed using standard Linux command-line utilities and scripted data collection.
Planned tools include:
•	top / htop – real-time process and CPU monitoring
•	free – memory usage tracking
•	df / iostat – disk usage and I/O performance
•	ip, ss, ping – network performance and latency
•	Custom SSH-based monitoring scripts (developed in later phases)
All monitoring data will be collected remotely from the workstation to ensure consistency with professional system administration practices.
________________________________________
2. Security Configuration Checklist
A security baseline checklist has been defined to guide the implementation of mandatory security controls in later weeks.
2.1 SSH Hardening
•	Disable password-based authentication
•	Enforce key-based authentication
•	Restrict SSH access to a single trusted IP address
•	Disable root login over SSH
•	Use non-default SSH configuration options where appropriate
________________________________________
2.2 Firewall Configuration
•	Enable a host-based firewall (UFW)
•	Allow SSH traffic only from the workstation IP
•	Deny all other inbound connections by default
•	Log dropped and rejected packets
________________________________________
2.3 Mandatory Access Control
•	Enable and configure AppArmor
•	Apply restrictive profiles to critical services
•	Monitor and log access control violations
________________________________________
2.4 Automatic Security Updates
•	Enable unattended security updates
•	Ensure timely application of critical patches
•	Verify update logs regularly
________________________________________
2.5 User and Privilege Management
•	Create a non-root administrative user
•	Enforce the principle of least privilege
•	Use sudo for administrative tasks
•	Disable direct root login where possible
________________________________________
2.6 Network Security
•	Limit exposed network services
•	Monitor open ports regularly
•	Validate firewall and access rules
________________________________________
3. Threat Model
A threat model was developed to identify realistic risks to the server and define appropriate mitigation strategies.
3.1 Identified Threats and Mitigations
Threat	Description	Mitigation Strategy
Brute-force SSH attacks	Automated login attempts targeting SSH	Key-based authentication, fail2ban, IP restrictions
Privilege escalation	Abuse of misconfigured permissions or services	Least-privilege users, AppArmor, sudo controls
Unauthorised network access	Exposure of unnecessary services or open ports	Firewall rules, service auditing, network isolation
________________________________________
3.2 Risk Assessment
•	SSH services represent the primary external attack surface
•	Misconfiguration poses a higher risk than software vulnerabilities
•	Continuous monitoring is required to detect abnormal behaviour
These risks will be reassessed following security implementation and audit phases.
________________________________________
4. Preparation for Secure Implementation
The planning carried out in Week 2 provides a structured framework for implementing and validating security controls in Weeks 4 and 5. By defining security requirements and testing methodologies early, configuration decisions can be evaluated quantitatively rather than subjectively.
________________________________________
Reflection
Key Planning Outcomes
•	Defined a clear and measurable performance testing strategy
•	Established a comprehensive security configuration baseline
•	Identified realistic operating system threats and mitigations
Anticipated Challenges
•	Balancing security controls with system performance
•	Avoiding excessive monitoring overhead
•	Ensuring consistent data collection across workloads
Learning Objectives Achieved
•	Understanding of operating system security threats
•	Ability to design security baselines and testing methodologies
•	Application of risk-based thinking to system planning
________________________________________
References
Linux Security Hardening Guide
https://linux-audit.com
SSH Essentials Documentation
https://www.ssh.com/academy/ssh

