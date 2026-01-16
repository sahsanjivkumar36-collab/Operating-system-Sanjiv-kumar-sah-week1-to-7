Week 1 — System Architecture & Environment Planning
Home | Week 1 | Week 2 →
________________________________________
Overview
Week 1 focuses on planning the system architecture and deployment environment for a headless Linux server prior to security hardening and performance testing. This phase establishes a secure and reproducible foundation by defining the host environment, virtualisation strategy, network topology, directory layout, and remote management approach.
Early architectural decisions directly influence system security, monitoring capability, and performance evaluation in later phases of the coursework.
________________________________________
Objectives
•	Design the overall dual-system architecture
•	Select and justify the host operating system and virtualisation platform
•	Define secure network configuration and IP addressing
•	Plan directory structure for automation and data collection
•	Prepare the environment for secure remote management via SSH
________________________________________
Deliverables
•	System architecture diagram
•	Virtualisation and network design documentation
•	Planned directory and repository structure
•	Evidence of host and virtual machine environment setup
________________________________________
1. System Architecture Design
1.1 High-Level Architecture
Architecture Description
The system consists of two logically separated machines:
•	Host system (macOS): Used as the workstation for administration, monitoring, and documentation
•	Guest system (Ubuntu Server LTS): Runs as a headless virtual machine without a graphical interface
•	Remote management: All server administration is performed via SSH
•	Network isolation: A VirtualBox host-only network is used to restrict access
This architecture mirrors professional server administration practices while reducing the server’s attack surface.
Screenshot / Diagram Filename:
week1-system-architecture.png
Figure W1-1: High-level system architecture illustrating the host machine, Linux server VM, and SSH-based management access.
________________________________________
1.2 Host Environment
Host System
•	Operating System: macOS
•	Role: Development workstation and administrative access point
Responsibilities
•	Establish SSH connections to the server
•	Execute monitoring and automation scripts
•	Capture command-line evidence and screenshots
•	Manage the GitHub Pages repository
Screenshot Filename:
week1-host-info.png
Figure W1-2: Host system information confirming the development environment.
________________________________________
2. Virtualisation Platform
2.1 VirtualBox Configuration
•	Virtualisation Software: Oracle VirtualBox
•	Guest Operating System: Ubuntu Server LTS
Planned Virtual Machine Resources
Resource	Allocation
CPU	2 vCPUs
Memory	2–4 GB RAM
Storage	20–40 GB (VDI)
These resource allocations provide sufficient capacity for security tooling and performance testing while remaining representative of lightweight server deployments.
Screenshot Filename:
week1-virtualbox-vm-settings.png
Figure W1-3: VirtualBox virtual machine configuration showing allocated CPU, memory, and storage resources.
________________________________________
2.2 Guest Operating System Selection
OS Selection Rationale
Ubuntu Server LTS was selected due to:
•	Long-term security updates and system stability
•	Extensive documentation and strong community support
•	Native AppArmor integration for mandatory access control
•	Compatibility with required tools such as UFW, fail2ban, and monitoring utilities
Screenshot Filename:
week1-ubuntu-server-installed.png
Figure W1-4: Ubuntu Server LTS installed and running without a graphical interface.
________________________________________
3. Network Design
3.1 Network Topology
•	Network Mode: Host-only Adapter
Design Rationale
•	Isolated from external and university networks
•	Secure and controlled SSH access
•	Predictable IP addressing for firewall configuration
•	Suitable for ethical security testing and demonstrations
Screenshot Filename:
workstationnat.png
Figure W1-5: Host-only network configuration within VirtualBox.
________________________________________
3.2 IP Addressing Plan
Component	IP Address
Workstation (Host)	192.168.56.102
Ubuntu Server VM	192.168.56.103
Static IP addressing ensures consistent SSH access and simplifies firewall rule creation in later phases.
Screenshot Filename:
week1-ip-config.png
Figure W1-6: IP configuration verification on the Ubuntu Server.
________________________________________
4. Directory and Repository Structure
4.1 Planned Server Directory Structure
/opt/project/
•	scripts/ – Automation and security verification scripts
•	data/ – Performance metrics and CSV outputs
•	logs/ – System and application logs
•	backups/ – Configuration and security backups
This structure promotes separation of concerns, clarity, and maintainability.
________________________________________
4.2 GitHub Repository Structure
Repository root:
•	README.md
•	docs/
o	week1.docx / week1.md
o	week2.docx / week2.md
o	week3.docx / week3.md
•	imagescreenshots/
o	week1/
o	week2/
•	scripts/
This layout supports GitHub Pages publication and clear weekly navigation.
________________________________________
5. Remote Management Plan
SSH Access Strategy
•	SSH enabled on the Ubuntu Server
•	Key-based authentication planned (implemented in Week 2)
•	Access restricted to the workstation IP address
•	Password-based authentication to be disabled
SSH will be used for:
•	System configuration and administration
•	Security hardening
•	Performance monitoring and testing
•	Evidence collection for coursework
________________________________________
6. Evidence: System Commands
The following commands were executed on the Ubuntu Server to document baseline system information:
•	uname -a (Screenshot: uname-a.png)
•	free -h (Screenshot: free-h.png)
•	df -h (Screenshot: df-h.png)
These commands provide insight into kernel version, memory availability, and filesystem capacity, which will inform later performance analysis.
________________________________________
Reflection
Key Design Decisions
•	Virtualisation: VirtualBox selected for stability and macOS compatibility
•	Networking: Host-only networking chosen to minimise attack surface
•	Operating System: Ubuntu Server LTS selected for security tooling and long-term support
Anticipated Challenges
•	Managing host resource constraints during performance testing
•	Maintaining consistent IP addressing
•	Ensuring clear and comprehensive evidence capture
Learning Objectives Achieved
•	Infrastructure planning before deployment
•	Understanding virtualisation and networking fundamentals
•	Designing secure-by-default environments
•	Structuring professional technical documentation
________________________________________
References
VirtualBox Documentation
https://www.virtualbox.org/manual/
Ubuntu Server Documentation
https://documentation.ubuntu.com/server/
  







